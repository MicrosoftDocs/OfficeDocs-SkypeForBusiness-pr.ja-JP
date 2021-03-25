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
description: Microsoft Teams でチームを保護するために、感度ラベルを使用する方法について説明します。
ms.openlocfilehash: 25c6e6a9a69f9172bebdab284754998e4acb910a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117195"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams の感度ラベル

[機密ラベルを使用](/microsoft-365/compliance/sensitivity-labels) すると、Teams 管理者は、チーム内での共同作業中に作成された機密性の高い組織コンテンツへのアクセスを保護し、規制することができます。 [Microsoft](/microsoft-365/compliance/go-to-the-securitycompliance-center)コンプライアンス センターで、関連するポリシーを使用して感度ラベルを構成した後、これらのラベルを組織内のチームに適用できます。

現在、Teams Education SKU を使用しているお客様は、感度ラベルはサポートされていません。 Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>区別ラベルと Teams の分類ラベルの違いは何ですか?

区別ラベルは、分類ラベル (Azure と呼ばれる)、グループAD異なります。 分類ラベルは、Microsoft 365 グループに関連付け可能なが、実際のポリシーが関連付け内にはないテキスト文字列です。 分類ラベルをメタデータとして使用し、内部ツールやスクリプトなどの他の方法を使用してポリシーを適用する必要があります。

感度ラベルを使用する利点は、ポリシーが Microsoft 365 グループ プラットフォーム、コンプライアンス センター、および Teams サービスの組み合わせを通じてエンドツーエンドで自動的に適用される点です。 機密ラベルは、組織の機密データをセキュリティで保護し、内部のポリシーまたは規制に準拠するための強力なインフラストラクチャ サポートを提供します。

現在分類ラベルを使用している場合は、詳細およびそれらを感度ラベルに移行する方法については、次のドキュメントを参照してください。従来の [Azure AD グループの分類](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>感度ラベルのシナリオ例

組織内の Teams で感度ラベルを使用する方法のシナリオ例:

- [チームのプライバシー レベル (パブリックまたはプライベート) を設定する](#set-the-privacy-level-for-teams)
- [チームへのゲスト アクセスを制御する](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>チームのプライバシー レベルを設定する

チームの作成中に適用すると、ユーザーが特定のプライバシー (パブリックまたはプライベート) 設定を持つチームを作成できる、感度ラベルを作成および構成できます。

たとえば、"機密" という名前の機密ラベルを作成して発行し、ラベルのプライバシー オプションが [非公開] として構成 **されている場合などです**。 その結果、このラベルで作成されたチームは、プライベート チームである必要があります。 

ユーザーが新しいチームを作成し、機密ラベルを選択すると、ユーザーが使用できるプライバシー オプションは [非公開]**のみです**。 パブリックや組織全体などの他のプライバシー オプションは、ユーザーが選択できません。

![機密ラベルのスクリーンショット](media/sensitivity-labels-confidential-example.png)

同様に、"全般" という名前の感度ラベルを作成して発行し、ラベルのプライバシー オプションを [パブリック] として構成 **します**。 ユーザーが新しいチームを作成すると、次のラベルを選択した場合にのみ、パブリックまたは組織全体のチームを作成できます。

![[一般的な感度] ラベルのスクリーンショット](media/sensitivity-labels-general-example.png)

チームが作成されると、チームのチャネルの右上隅に感度ラベルが表示されます。 "Confidential\Finance" などの階層的な親の子ラベルを使用している場合は、親ラベルだけがチャネル ヘッダーに表示されます。


![チーム チャネルの感度ラベルのスクリーンショット](media/sensitivity-labels-channel.png)

チーム所有者は、チームにアクセスして [チームの編集] をクリックすると、いつでもチームの感度ラベルとプライバシー設定を **変更できます**。

![チームプロパティの感度ラベルのスクリーンショット](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>チームへのゲスト アクセスを制御する

チームへのゲスト アクセスを制御するには、感度ラベルを使用できます。 ゲスト アクセスを許可しないラベルで作成された Teams は、組織内のユーザーだけが使用できます。 組織外のユーザーをチームに追加できない。

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams 管理センター

Microsoft Teams 管理センターでチームを作成または編集するときに、感度ラベルを適用できます。 

また、チームのプロパティおよび Microsoft Teams 管理センターの [チームの管理] ページの [分類] 列にも、感度ラベルが表示されます。

## <a name="limitations"></a>制限事項

Teams の感度ラベルを使用する前に、次の制限事項に注意してください。

- **サブラベルに親ラベル名が表示されない**
    
    Teams はサブラベルをサポートしますが、親ラベルの名前は表示されません。 たとえば、機密のすべての **従業員** \\ **は、すべての従業員****として表示されます**。

- **Teams Graph API、PowerShell コマンドレット、およびテンプレートでは、感度ラベルはサポートされません。**
    
    ユーザーは、Teams Graph API、Teams PowerShell コマンドレット、および Teams テンプレートを使用して直接作成されたチームに、感度ラベルを適用することはできません。

- **プライベート チャネルのサポート**
    
    チームで作成されたプライベート チャネルは、チームに適用された感度ラベルを継承します。 プライベート チャネルの SharePoint サイト コレクションにも同じラベルが自動的に適用されます。
    
    ただし、ユーザーがプライベート チャネルの SharePoint サイトの感度ラベルを直接変更した場合、そのラベルの変更は Teams クライアントには反映されません。 このシナリオでは、ユーザーはプライベート チャネル ヘッダーにチームに適用された元の感度ラベルを引き続き表示します。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Teams の感度ラベルを作成および構成する方法

Microsoft 365 ドキュメントの手順を使用して、Teams の感度ラベルを作成および構成します。 

- [Microsoft Teams、Microsoft 365 グループ、SharePoint](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)サイトのコンテンツを保護するには、感度ラベルを使用します。