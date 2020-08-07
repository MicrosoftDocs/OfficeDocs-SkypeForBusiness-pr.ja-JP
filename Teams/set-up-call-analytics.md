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
description: Microsoft Teams の通話品質の問題を特定してトラブルシューティングするために、ユーザーごとの通話分析をセットアップします。
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581108"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Microsoft Teams の通話分析を設定する

Microsoft Teams の管理者は、ユーザーごとの通話分析を使用して、**個々のユーザー**に対するチームの通話品質と接続の問題のトラブルシューティングを行うことができます。 通話分析を最大限に活用するには、次のように設定します。
  
- 特別なサポートロールを、ヘルプデスクエージェントなどのユーザーに割り当てて、ユーザーに対して通話分析を表示できるようにします。 これらのサポートロールは、Teams 管理センターの残りの部分にはアクセスできません。 
    
- .Tsv または .csv データファイルをアップロードして、建物、サイト、テナントの情報をユーザーごとの通話分析に追加します。
    
ユーザーごとの通話分析の使用を開始する準備ができたら、「[ユーザーごとの通話分析を使用して通話品質の低下を解決する」を](use-call-analytics-to-troubleshoot-poor-call-quality.md)参照してください。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>サポートおよびヘルプデスクスタッフへのアクセス許可を付与する

Teams の管理者は、すべてのユーザーについて分析情報を取得するための完全なアクセス権を持っています。 ユーザーがユーザーごとの通話分析にアクセスできるように、チーム管理センターの他の部分にはアクセスできないようにするために、ユーザーが1人ずつの通話分析にも割り当てることができる特別な Azure Active Directory ロールを作成しました。 ユーザーごとの通話分析 (Tier 1 サポート) の制限されたビューが必要なユーザーに**チーム通信のサポートスペシャリスト**の役割を割り当てます。 ユーザー単位の通話分析 (Tier 2 サポート) へのフルアクセスが必要なユーザーに、 **Teams 通信サポートエンジニア**の役割を割り当てます。 どちらのロールでも、Teams 管理センターの残りの部分にはアクセスできません。

これらの各ロールの概要については、「[各チームでサポート](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)される役割」を参照してください。

Teams の管理者ロールの詳細については、「チーム管理[者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。 Azure Active Directory に管理者ロールを割り当てる方法については、「 [Azure Active directory でロールを表示して割り当てる](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。

Azure Active Directory に管理者ロールを割り当てる方法については、「 [Azure Active directory での役割の表示と割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>.Tsv または .csv ファイルをアップロードして、建物、サイト、テナントの情報を追加する

.Csv または .tsv ファイルをアップロードすることによって、建物、サイト、テナントの情報をユーザーごとの呼び出し分析に追加することができます。 すべての情報を使って、通話分析で IP アドレスを物理的な場所に対応付けることができます。 管理者およびヘルプデスクエージェントは、この情報を使って、通話の問題に関する傾向を見つけることができます。 たとえば、同じ建物のユーザーが同様の通話品質の問題を抱えているのはなぜですか? 

チームまたは Skype for business の管理者である場合は、Teams または Skype for Business 通話品質ダッシュボード (CQD) から既存のテナントと建物データファイルを使用できます。 まず、CQD からファイルをダウンロードしてから、通話分析にアップロードします。 

- 既存のデータファイルをダウンロードするには、 **Microsoft Teams 管理センター**の  >  **通話品質ダッシュボード**  >  **で今すぐアップロード**します。 [**マイアップロード**] ボックスの一覧で、目的のファイルの横にある [**ダウンロード**] をクリックします。 

- 新しいファイルをアップロードするには、 **Microsoft Teams 管理センター**の場所に移動し、  >  **Locations**[**場所データのアップロード**] または [**場所のデータの置き換え**] を選択します。
  
.Tsv または .csv ファイルを最初から作成する場合は、「[テナントと建物データをアップロード](CQD-upload-tenant-building-data.md)する」を参照してください。
  
## <a name="related-topics"></a>関連トピック

[ユーザーごとの通話分析を使用して、低品質の通話品質をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
