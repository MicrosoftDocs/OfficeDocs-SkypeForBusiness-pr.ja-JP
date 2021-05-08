---
title: Microsoft Teams の感度ラベル
ms.author: mikeplum
author: cabailey
manager: laurawi
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
description: 感度ラベルを使用してチームを保護する方法についてMicrosoft Teams。
ms.openlocfilehash: 461daf6e91f9ba276dceef1929601d1188563931
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593865"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams の感度ラベル

[機密ラベルを使用](/microsoft-365/compliance/sensitivity-labels)するとTeamsチーム内の共同作業中に作成された機密性の高い組織のコンテンツへのアクセスを保護および規制できます。 [Microsoft](/microsoft-365/compliance/go-to-the-securitycompliance-center)コンプライアンス センターで、関連付けられているポリシーで感度ラベルを構成した後、これらのラベルを組織内のチームに適用できます。

現在、Teams Education SKU を使用しているお客様のクラス チームでは、感度ラベルはサポートされていません。 Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>感度ラベルと分類ラベルの違Teamsは何ですか?

感度ラベルは、分類ラベルとは異なります。分類ラベルは、Azure AD分類とも呼ばれる。 分類ラベルは、特定のグループに関連付Microsoft 365、実際のポリシーが関連付けられているものはないテキスト文字列です。 分類ラベルをメタデータとして使用し、内部ツールやスクリプトなどの他の方法を使用してポリシーを適用する必要があります。

感度ラベルを使用する利点は、ポリシーが Microsoft 365 Groups プラットフォーム、コンプライアンス センター、および Teams サービスの組み合わせによってエンド to エンドで自動的に適用されるという利点があります。 機密ラベルは、組織の機密データをセキュリティで保護し、社内のポリシーまたは規制に準拠するための強力なインフラストラクチャ サポートを提供します。

現在分類ラベルを使用している場合は、感度ラベルに移行する方法の詳細と手順については、次のドキュメントを参照してください。クラシック Azure AD [グループ分類](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>感度ラベルのシナリオ例

組織内のユーザーと一緒に感度ラベルを使用Teamsシナリオの例を次に示します。

- [チームのプライバシー レベル (パブリックまたはプライベート) を設定する](#set-the-privacy-level-for-teams)
- [チームへのゲスト アクセスを制御する](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>チームのプライバシー レベルを設定する

チームの作成時に適用すると、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を持つチームを作成できる、感度ラベルを作成して構成できます。

たとえば、"Confidential" という名前の機密ラベルを作成して発行します。このラベルには、ラベルのプライバシー オプションが Private として構成 **されています**。 その結果、このラベルで作成されたチームは、プライベート チームである必要があります。 

ユーザーが新しいチームを作成し **、[Confidential]** ラベルを選択すると、ユーザーが使用できるプライバシー オプションは [プライベート] **のみです**。 [パブリック] や [組織全体] などの他のプライバシー オプションは、ユーザーが選択できません。

![機密ラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

同様に、ラベル プライバシー オプションがパブリック として構成されている "General" という名前の感度ラベルを作成して発行 **します**。 ユーザーが新しいチームを作成すると、次のラベルを選択した場合にのみ、パブリックまたは組織全体のチームを作成できます。

![一般的な感度ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

チームが作成されると、チーム内のチャネルの右上隅に感度ラベルが表示されます。 

> [!NOTE]
> "Confidential\Finance" などの階層的な親子ラベルを使用している場合は、親ラベルだけがチャネル ヘッダーに表示されます。

![チーム チャネルの感度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

チーム所有者は、チームにアクセスしてチームの感度ラベルとプライバシー設定をいつでも変更し、[チームの編集] を **クリックします**。

![チームのプロパティの感度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>チームへのゲスト アクセスを制御する

感度ラベルを使用して、チームへのゲスト アクセスを制御できます。 Teamsアクセスを許可しないラベルで作成されたユーザーは、組織内のユーザーだけが使用できます。 組織外のユーザーをチームに追加できない。

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams 管理センター

管理者センターでチームを作成または編集するときに、Microsoft Teams適用できます。 

また、チームのプロパティや、管理センターの [チームの管理]ページの [分類] Microsoft Teams表示されます。

## <a name="limitations"></a>制限事項

感度ラベルを使用する前Teams、次の制限事項に注意してください。

- **親ラベル名がサブラベルに対して表示されない**
    
    Teamsはサブラベルをサポートしますが、親ラベルの名前は表示されません。 たとえば、Confidential  \\ **All Employees は [All Employees]** **と表示されます**。

- **感度ラベルは、TEAMS GRAPH Api、PowerShell コマンドレット、およびテンプレートではサポートされていません**
    
    ユーザーは、Teams Graph API、powerShell コマンドレット、Teams テンプレートを使用してチームを直接作成する際に、Teamsできません。 ただし、Modern Groups Graph API と PowerShell コマンドレットを使用すると、ラベル付きのグループを作成できます。 そのため、ユーザーはまず Groups Graph API または PowerShell コマンドレットを使用してラベル付きグループを作成し、次にこれらのグループを Teams。

- **プライベート チャネルのサポート**
    
    チームで作成されたプライベート チャネルは、チームに適用された感度ラベルを継承します。 同じラベルが、プライベート チャネルの SharePointに自動的に適用されます。
    
    ただし、ユーザーがプライベート チャネルの SharePoint サイトの感度ラベルを直接変更した場合、そのラベルの変更は Teams クライアントに反映されません。 このシナリオでは、ユーザーはプライベート チャネル ヘッダーでチームに適用された元の感度ラベルを引き続き表示します。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>デバイスの感度ラベルを作成して構成するTeams

次のドキュメントの手順に従ってMicrosoft 365の感度ラベルを作成して構成Teams。 

- [感度ラベルを使用して、Microsoft Teams、Microsoft 365、](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)および SharePoint サイト内のコンテンツを保護します。
