---
title: Microsoft Teams の感度ラベル
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で感度ラベルを定義して使用する方法について説明します。
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795778"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams の感度ラベル

[機密ラベルを使用](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) すると、Teams 管理者は、チーム内での共同作業中に作成された機密性の高い組織コンテンツへのアクセスを規制できます。 コンプライアンス センターで、感度ラベルと関連するポリシーを [定義できます](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。 これらのラベルとポリシーは、組織内のチームに自動的に適用されます。  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>区別ラベルと Teams の分類ラベルの違いは何ですか?

区別ラベルは、分類ラベルとは異なります。 分類ラベルは、Microsoft 365 グループに関連付け可能なが、実際のポリシーが関連付けられているものはないテキスト文字列です。 分類ラベルをメタデータとして使用して、内部ツールとスクリプトを使用してポリシーを手動で適用します。

一方、感度ラベルとそのポリシーは、グループ プラットフォーム、セキュリティ & コンプライアンス センター、および Teams サービスの組み合わせを通じて、エンドツーエンドで自動的に適用されます。 機密ラベルは、組織の機密データをセキュリティで保護するための強力なインフラストラクチャ サポートを提供します。  

既存のグループを分類ラベルの使用から感度ラベルの使用に移行するには [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)グループの Azure Active Directory の分類と感度ラベルの手順を使用します。

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Teams の感度ラベルを作成、管理、発行する

Teams の感度ラベルを有効にし、作成し、発行する方法については [、「Microsoft Teams、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)グループ、および SharePoint サイトのコンテンツを保護するために、感度ラベルを使用する」を参照してください。

>[!IMPORTANT]
>感度ラベルを作成、更新、削除するには、ユーザーにラベルを発行する際に注意深く注意する必要があります。 シーケンスにずれが生じ、すべてのユーザーに永続的なチーム作成エラーが発生する可能性があります。 したがって、ラベルの作成と発行、発行済みラベル<a href="#createpublishlabels"></a>の変更と削除、<a href="#modifydeletelabels"></a>チームの作成エラーの管理を行う場合は、次の操作<a href="#manageerrors">を行う必要があります</a>。

**ラベルを作成して発行する**<a name="createpublishlabels"></a>

コンプライアンス センターでラベルを作成して公開すると、ラベルがチームの作成インターフェイスに表示されるのに最大 10 分かかる場合があります。 次の手順に従って、テナント内のすべてのユーザーにラベルを発行します。
1. ラベルを作成し、テナント内のいくつかの選択したユーザー アカウントに対して発行します。
2. ラベルが公開された場合は、10 分待ちます。
3. 10 分後に、ラベルにアクセスできるユーザー アカウントのいずれかを使用して、ラベル付きチームを作成してみてください。
4. 手順 3 でチームが正常に作成された場合は、先に進み、テナント内の残りのユーザーのラベルを発行します。

**発行済みラベルを変更および削除する**<a name="modifydeletelabels"></a>

ラベルが感度ポリシーに関連付けられている間にラベルを削除または変更すると、テナント全体でチームの作成に失敗する可能性があります。 そのため、ラベルを削除または変更する前に、最初にラベルと関連付けられているポリシーの関連付けを解除する必要があります。 次の手順を使用する  
を選択してラベルを削除または変更します。
1. ラベルを使用しているすべてのポリシーからラベルを削除します。 または、ポリシー自体を削除できます。
2. ラベルがポリシーから削除された場合、またはポリシー自体が削除された場合は、さらに進むまで 10 分待ちます。
3. 10 分後に、チーム作成インターフェイスを起動し、テナント内のユーザーにラベルが表示されなくなったら確認します。
4. これで、ラベルを安全に削除または変更できます。

**チームの作成エラーを管理する**<a name="manageerrors"></a>

パブリック プレビュー中にチームの作成が失敗し始める場合は、次の 2 つのオプションがあります。
 - チームの作成中に、どのユーザーにも、感度ラベルが必須でなからず確認します。
 - [このプレビューを有効にする] のスクリプトを使用して、 [感度ラベルをオフにします](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)。

EnableMIPLabels の設定は、次のように false に設定する必要があります。

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Teams で感度ラベルを使用する

組織内の Teams で感度ラベルを使用する方法のシナリオ例を次に示します。

### <a name="privacy-setting-of-teams"></a>チームのプライバシー設定

チームの作成中に適用した場合、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を持つチームを作成できる、感度ラベルを作成できます。

たとえば、セキュリティ & コンプライアンス センターで "Confidential" というラベルを作成し、このラベルで作成されたチームをプライベート チームに設定します。 ユーザーが新しいチームを作成し、機密ラベルを選択すると、ユーザーが使用できるプライバシー オプションは [プライベート]**のみです**。 パブリックや組織全体などの他のプライバシー オプションは、ユーザーに対して無効になります。

![機密ラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

同様に、ユーザーが新しいチームを作成するときに [全般] を選択した場合、パブリックチームまたは組織全体のチームのみを作成できます。

![[一般的な感度] ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

チームが作成されると、チームのチャネルの右上隅に感度ラベルが表示されます。

![チーム チャネルの感度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

チーム所有者は、チームにアクセスし、[チームの編集] をクリックすると、いつでもチームの感度ラベルとプライバシー設定を **変更できます**。

![チームプロパティの感度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>チームへのゲスト アクセス

特定のラベルで作成されたチームでゲスト アクセスを許可するかどうかを指定できます。 ゲスト アクセスを許可しないラベルで作成された Teams は、組織内のユーザーだけが使用できます。 組織外のユーザーをチームに追加できない。

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの感度ラベル

Microsoft Teams 管理センターでチームを作成または編集するときに、感度ラベルを設定できます。 また、チームのプロパティおよび Microsoft Teams 管理センターの [チームの管理] ページの [分類] 列にも、感度ラベルが表示されます。

## <a name="known-issues"></a>既知の問題

**Teams Graph API、PowerShell コマンドレット、テンプレートでの感度ラベルのサポート**

現在、ユーザーは、Graph API、PowerShell コマンドレット、およびテンプレートを使用して直接作成されたチームに、感度ラベルを適用することはできません。

**Teams EDU SKU での感度ラベルのサポート**

現在、Teams Education SKU を使用しているお客様は、感度ラベルはサポートされていません。

**プライベート チャネル用に SharePoint サイト コレクションで直接感度ラベルを編集する**

チームで作成されたプライベート チャネルは、チームに適用された感度ラベルを継承します。 さらに、プライベート チャネルの SharePoint サイト コレクションにも同じラベルが自動的に適用されます。

ユーザーがプライベート チャネルの SharePoint サイト コレクションの感度ラベルを直接更新した場合、そのラベルは Teams クライアントでは更新されません。 このシナリオでは、ユーザーはプライベート チャネル ヘッダーにチームに適用された感度ラベルを引き続き表示します。

**Teams アプリ以外の感度ラベルに適用された変更の反映時間**

Teams アプリ以外の感度ラベルに加えた変更は、Teams アプリに反映するために最大 24 時間かかる場合があります。 これは、テナントのラベルを有効または無効にする変更、ラベル名、設定、ポリシーの変更に適用されます。

さらに、チームをバックアップするグループまたは SharePoint サイト コレクションに直接行われたラベルに対する変更は、Teams アプリに反映されるのに最大 24 時間かかることがあります。
