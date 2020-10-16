---
title: Microsoft Teams の機密ラベル
author: lanachin
ms.author: v-lanac
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
description: Microsoft Teams で機密ラベルを定義して使用する方法について説明します。
ms.openlocfilehash: 21d70bf48448ccef5555078e4aba65bb10d5d6a2
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476722"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams の機密ラベル

機密[ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)を使用すると、チームの管理者はチーム内で共同作業を行って作成された機密組織のコンテンツへのアクセスを規制できます。 [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)では、機密ラベルと関連するポリシーを定義できます。 このようなラベルとポリシーは、組織内の teams に自動的に適用されます。  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>秘密度ラベルとチーム分類ラベルの違いは何ですか?

機密ラベルは、PowerShell を使って作成する必要がある分類ラベルとは異なります。 分類ラベルは、グループに関連付けることができるが、実際のポリシーは関連付けられていないテキスト文字列です。 分類ラベルはメタデータとして使用し、内部のツールとスクリプトを使って手動でポリシーを適用します。

一方、機密ラベルとそのポリシーは、グループプラットフォーム、セキュリティ & コンプライアンスセンター、および Teams サービスの組み合わせによって、自動的にエンドツーエンドで適用されます。 機密ラベルを使用すると、組織の機密データをセキュリティで保護するための強力なインフラストラクチャサポートが提供されます。  

分類ラベルを使用して、機密ラベルを使用して既存のグループを移行するには、「 [Microsoft 365 グループの Azure Active Directory の分類と秘密度ラベル](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)」の手順を使用します。
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Teams の機密ラベルを作成、管理、および公開する

Teams の機密ラベルを有効にし、作成して発行する方法については、「 [Microsoft 365 グループの Azure Active Directory の分類と機密ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」を参照してください。

>[!IMPORTANT]
>機密ラベルの作成、更新、削除には、ユーザーにラベルを発行するための順序を慎重に付ける必要があります。 順序を逸脱すると、すべてのユーザーに対して永続的なチーム作成エラーが発生する可能性があります。 したがって、 <a href="#createpublishlabels">ラベルの作成と発行</a>、発行された <a href="#modifydeletelabels">ラベルの変更と削除</a>、 <a href="#manageerrors">チーム作成エラーの管理</a>を行う場合は、次の操作を実行することが重要です。

<a name="createpublishlabels"> </a> **ラベルを作成して発行する**

セキュリティ & コンプライアンスセンターでラベルを作成して公開すると、チーム作成インターフェイスでラベルが表示されるまでに最大10分かかることがあります。 テナントのすべてのユーザーのラベルを発行するには、次の手順を実行します。
1. ラベルを作成して、テナント内のいくつかの選択されたユーザーアカウントに公開します。
2. ラベルが公開されたら、10分待ちます。
3. 10分後に、ラベルにアクセスできるいずれかのユーザーアカウントを使用して、ラベルを含むチームを作成してみてください。
4. 手順3でチームが正常に作成された場合は、テナントに残りのユーザーのラベルを公開します。

<a name="modifydeletelabels"> </a> **公開したラベルを変更および削除**する

機密ポリシーに関連付けられているラベルを削除または変更すると、テナントでのチームの作成エラーが発生する可能性があります。 したがって、ラベルを削除または変更する前に、最初にラベルと関連付けられているポリシーの関連付けを解除する必要があります。 次の手順を使用します。  
ラベルを削除または変更するには、次の操作を行います。
1. ラベルを使用するすべてのポリシーからラベルを削除します。 または、ポリシー自体を削除することもできます。
2. ラベルをポリシーから削除するか、ポリシー自体を削除したら、10分待ってからさらに進みます。
3. 10分後に、チーム作成インターフェイスを起動し、テナント内のユーザーのラベルが表示されなくなったことを確認します。
4. これで、ラベルを安全に削除または変更できます。

**チーム作成エラー** <a name="manageerrors"> </a>を管理する

パブリックプレビューの途中でチームの作成が失敗する場合は、次の2つのオプションがあります。
 - チームを作成するときに、すべてのユーザーが秘密度のラベルを必須にしないようにします。
 - 「 [このプレビューを有効にする](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)」のスクリプトを使用して、機密ラベルをオフにします。

EnableMIPLabels の設定は、次のように false に設定する必要があることに注意してください。

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Teams で秘密度ラベルを使用する

組織内の Teams で機密ラベルを使用する方法の例を次に示します。

### <a name="privacy-setting-of-teams"></a>Teams のプライバシー設定

チームの作成時に適用される機密ラベルを作成して、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を使用してチームを作成できるようにすることができます。

たとえば、セキュリティ & コンプライアンスセンターで "社外秘" という名前のラベルを作成し、このラベルを使って作成されたチームがプライベートチームでなければならないようにチームを構成します。 ユーザーが新しいチームを作成して、 **機密** ラベルを選択した場合、ユーザーが使用できるプライバシーオプションのみが **非公開**になります。 パブリックや組織全体など、その他のプライバシーオプションは、ユーザーに対して無効になります。

![秘密度のラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

同様に、ユーザーが新しいチームを作成するときに **[一般** ] を選択した場合、パブリックまたは組織全体のチームのみを作成できます。

![一般的な秘密度ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

チームが作成されると、チーム内のチャネルの右上隅に [秘密度] ラベルが表示されます。

![チームチャネルの秘密度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

チーム所有者は、チームに移動し、[ **チームの編集**] をクリックして、いつでもチームの機密ラベルとプライバシー設定を変更することができます。

![チームチャネルの秘密度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Teams へのゲストアクセス

特定のラベルを使用して作成されたチームがゲストアクセスを許可するかどうかを指定できます。 ゲストアクセスが許可されていないラベルで作成されたチームは、組織内のユーザーのみが利用できます。 組織外のユーザーをチームに追加することはできません。

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの機密ラベル

Microsoft Teams 管理センターでチームを作成または編集するときに、機密ラベルを設定することができます。 機密ラベルは、チームのプロパティと、Microsoft Teams 管理センターの [チームの管理] ページの [ **分類** ] 列にも表示されます。

## <a name="known-issues"></a>既知の問題

**Teams Graph Api、Powershell コマンドレット、テンプレートでの機密ラベルのサポート**

現時点では、ユーザーは、Graph Api、Powershell コマンドレット、およびテンプレートを使って直接作成されたチームに機密ラベルを適用することはできません。

**Teams EDU Sku での機密ラベルのサポート**

機密ラベルは、現在、Teams の教育 Sku を使用しているお客様はサポートされていません。

**SharePoint サイトコレクションでプライベートチャネルの機密ラベルを直接編集する**

チーム内で作成されたプライベートチャネルは、チームに適用された機密ラベルを継承します。 さらに、同じラベルが、プライベートチャネルの SharePoint サイトコレクションに自動的に適用されます。

プライベートチャネルの SharePoint サイトコレクションの機密ラベルがユーザーによって直接更新された場合、そのラベルは Teams クライアントでは更新されません。 このシナリオでは、ユーザーはプライベートチャネルヘッダーのチームに適用された機密ラベルを引き続き表示します。

**Teams アプリ外部の機密ラベルに適用された変更の伝達時間**

Teams アプリ以外の機密ラベルに対する変更は、Teams アプリで反映されるまでに最大24時間かかることがあります。 これは、テナントのラベルの有効化または無効化、ラベル名、設定、ポリシーの変更に適用されます。

さらに、チームをバックアップするグループまたは SharePoint サイトコレクションに直接追加されたラベルに対する変更は、Teams アプリに反映されるまでに最大24時間かかることがあります。
