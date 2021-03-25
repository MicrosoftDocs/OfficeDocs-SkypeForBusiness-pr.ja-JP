---
title: Microsoft Teams の通話分析を設定する
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Microsoft Teams の通話品質の問題を特定してトラブルシューティングするために、ユーザーごとの通話分析を設定します。
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117135"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Microsoft Teams の通話分析を設定する

Microsoft Teams 管理者は、ユーザーごとの通話分析を使用して、個々のユーザーの Teams の通話品質と接続の問題を **トラブルシューティングできます**。 通話分析をフルに活用するには、次の設定を行います。
  
- ヘルプデスク エージェントなどの特殊なサポート ロールをユーザーに割り当て、ユーザーの通話分析を表示します。 これらのサポート ロールは、Teams 管理センターの他の部分にはアクセスできない。 
    
- .tsv または .csv データ ファイルをアップロードして、ユーザーごとの通話分析に建物、サイト、テナントの情報を追加します。
    
ユーザーごとの通話分析の使用を開始する準備ができたら、「ユーザーごとの通話分析を使用して低品質の通話のトラブルシューティングを行う」を参照 [してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>サポートおよびヘルプデスク スタッフにアクセス許可を付与する

Teams 管理者は、すべてのユーザーの通話分析情報にフル アクセスできます。 サポート スタッフとヘルプデスク エージェントに割り当て、(Teams 管理センターの他の部分にアクセスすることなく) ユーザーごとの通話分析にアクセスできるよう、いくつかの特殊な Azure Active Directory ロールを作成しました。 ユーザーごとの **通話分析 (** 階層 1 のサポート) のビューを限定する必要があるユーザーに、Teams 通信サポートの専門の役割を割り当てる。 ユーザーごとの **通話分析 (** 階層 2 のサポート) へのフル アクセスが必要なユーザーに、Teams コミュニケーション サポート エンジニアの役割を割り当てる。 どちらの役割も、Teams 管理センターの他の部分にアクセス権を持つ必要があります。

これらの各役割の機能については、「Teams の各サポートの役割について [」を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)。

Teams の管理者ロールの詳細については、「Teams 管理者ロールを使用して Teams を [管理する」を参照してください](using-admin-roles.md)。 Azure Active Directory で管理者ロールを割り当てる方法については、「Azure Active Directory でロールを表示して割り当てる [」を参照してください](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

Azure Active Directory で管理ロールを割り当てる方法については、「Azure Active Directory でロールを表示および割り当てる [」を参照してください](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>.tsv または .csv ファイルをアップロードして、建物、サイト、テナント情報を追加する

.csv ファイルまたは .tsv ファイルをアップロードすると、ユーザーごとの通話分析に建物、サイト、テナントの情報を追加できます。 これらの情報はすべて、通話分析によって IP アドレスを物理的な場所にマップできます。 管理者とヘルプデスク エージェントは、この情報を使用して通話の問題の傾向を把握できます。 たとえば、同じ建物内のユーザーが同様の通話品質の問題を抱えている理由は何ですか? 

Teams または Skype for Business 管理者の場合は、既存のテナントを使用して、Teams または Skype for Business 通話品質ダッシュボード (CQD) からデータ ファイルを作成できます。 まず、CQD からファイルをダウンロードし、それを通話分析にアップロードします。 

- 既存のデータ ファイルをダウンロードするには **、Microsoft Teams** 管理センターの [通話品質ダッシュボードのアップロード]  >    >  **に移動します**。 [マイ **アップロード] リストで、** 必要なファイル **の** 横にある [ダウンロード] をクリックします。 

- 新しいファイルをアップロードするには **、Microsoft Teams** 管理センターの [場所] に移動し、[場所データのアップロード] または [場所データの置き換  >  え]**を選択します**。 
  
.tsv または .csv ファイルを最初から作成する場合は、「テナントをアップロードしてデータを作成する [」を参照してください](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>関連項目

[低品質の通話のトラブルシューティングにユーザーごとの通話分析を使用する](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)