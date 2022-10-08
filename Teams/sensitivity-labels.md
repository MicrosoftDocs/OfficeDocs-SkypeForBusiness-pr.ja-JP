---
title: Microsoft Teams の秘密度ラベル
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- tier1
- purview-compliance
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 秘密度ラベルを使用して Microsoft Teams のチームを保護する方法について説明します。
ms.openlocfilehash: 59bd67ea59787a1f73b2a0c808bfa3464c3bc31b
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046877"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams の秘密度ラベル

[秘密度ラベル](/microsoft-365/compliance/sensitivity-labels) を使用すると、Teams 管理者は、チーム内での共同作業中に作成された機密性の高い組織コンテンツへのアクセスを保護および規制できます。 [Microsoft Purview コンプライアンス ポータル](/microsoft-365/compliance/go-to-the-securitycompliance-center)に関連付けられたポリシーを使用して秘密度ラベルを構成した後、これらのラベルを組織内のチームに適用できます。

現在、Teams Education SKU を使用しているお客様のクラス チームでは、秘密度ラベルはサポートされていません。 Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>秘密度ラベルと Teams 分類の違いは何ですか?

秘密度ラベルは Teams の分類とは異なり、Azure AD グループ分類とも呼ばれます。 分類は、Microsoft 365 グループに関連付けることができるが、実際のポリシーが関連付けられていないテキスト文字列です。 メタデータとして分類を使用し、内部ツールやスクリプトなどの他のメソッドを使用してポリシーを適用する必要があります。

秘密度ラベルを使用する利点は、Microsoft 365 グループ プラットフォーム、Microsoft Purview コンプライアンス ポータル、Teams サービスの組み合わせによって、ポリシーがエンド ツー エンドで自動的に適用されることです。 秘密度ラベルは、組織の機密データをセキュリティで保護し、内部ポリシーまたは規制に準拠するための強力なインフラストラクチャ サポートを提供します。

Teams 分類を現在使用している場合は、これらの値を秘密度ラベルに変換する方法の詳細と手順については、次のドキュメントを参照してください。 [クラシック Azure AD グループ分類](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>秘密度ラベルのシナリオの例

組織内の Teams で秘密度ラベルを使用する方法のシナリオの例を次に示します。

- [チームのプライバシー レベル (パブリックまたはプライベート) を設定する](#set-the-privacy-level-for-teams)
- [チームへのゲスト アクセスを制御する](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>チームのプライバシー レベルを設定する

秘密度ラベルを作成して構成し、チームの作成時に適用すると、ユーザーは特定のプライバシー (パブリックまたはプライベート) 設定を持つチームを作成できます。

たとえば、"Confidential" という名前の秘密度ラベルを作成して公開し、ラベルのプライバシー オプションを **Private** として構成します。 その結果、このラベルを使用して作成されたすべてのチームは、プライベート チームである必要があります。 

ユーザーが新しいチームを作成し、 **機密** ラベルを選択すると、ユーザーが使用できる唯一のプライバシー オプションは **Private です**。 [パブリック] や [組織全体] などの他のプライバシー オプションは、ユーザーが選択することはできません。

![機密機密ラベルのスクリーンショット。](media/sensitivity-labels-confidential-example.png)

同様に、ラベルのプライバシー オプションがパブリックとして構成されている "General" という名前の秘密度ラベルを作成して公開 **します**。 ユーザーが新しいチームを作成すると、次のラベルを選択した場合にのみ、パブリックチームまたは組織全体のチームを作成できます。

![一般的な秘密度ラベルのスクリーンショット。](media/sensitivity-labels-general-example.png)

チームが作成されると、秘密度ラベルはチーム内のチャネルの右上隅のユーザーに表示されます。 

![チーム チャネルの秘密度ラベルのスクリーンショット。](media/sensitivity-labels-channel.png)

チームの所有者は、チームに移動してチームの秘密度ラベルとプライバシー設定をいつでも変更し、[ **チームの編集]** をクリックできます。

![チームプロパティの秘密度ラベルのスクリーンショット。](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>チームへのゲスト アクセスを制御する

秘密度ラベルを使用して、チームへのゲスト アクセスを制御できます。 ゲスト アクセスを許可しないラベルで作成された Teams は、組織内のユーザーのみが使用できます。 組織外のPeopleをチームに追加することはできません。

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams 管理センター

秘密度ラベルは、Microsoft Teams 管理センターでチームを作成または編集するときに適用できます。 秘密度ラベルは、チームのプロパティや、Microsoft Teams 管理センターの [**チームの管理**] ページの **[分類**] 列にも表示されます。

## <a name="limitations"></a>制限事項

Teams で秘密度ラベルを使用する前に、次の制限事項に注意してください。

- **秘密度ラベルは Teams Graph API および PowerShell コマンドレットではサポートされていません**
    
    Teams Graph API または Teams PowerShell コマンドレットを使用してチームを直接作成するときに、ユーザーは秘密度ラベルを指定できません。 ただし、Modern Groups Graph API と PowerShell コマンドレットでは、機密ラベルを持つグループを作成できます。 つまり、これらのメソッドを使用して秘密度ラベルを持つグループを作成し、これらのグループをチームに変換できます。

- **プライベート チャネルのサポート**
    
    チームで作成されたプライベート チャネルは、チームに適用された秘密度ラベルを継承します。 プライベート チャネルの SharePoint サイト コレクションには、同じラベルが自動的に適用されます。
    
    ただし、ユーザーがプライベート チャネルの SharePoint サイトの秘密度ラベルを直接変更した場合、そのラベルの変更は Teams クライアントに反映されません。 このシナリオでは、ユーザーはプライベート チャネル ヘッダーでチームに適用された元の秘密度ラベルを引き続き表示します。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Teams の秘密度ラベルを作成して構成する方法

Microsoft Purview のドキュメントの手順を使用して、Teams の秘密度ラベルを作成および構成します。 

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)します。
