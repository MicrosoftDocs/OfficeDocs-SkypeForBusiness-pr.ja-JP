---
title: Microsoft Teamsの呼び出し分析を設定する
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 通話品質の問題を特定してトラブルシューティングするために、ユーザーごとの通話分析Microsoft Teams設定します。
ms.openlocfilehash: be93a24f7d18e5b347c6375622ca47c3bdaeae26
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556478"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Microsoft Teamsの呼び出し分析を設定する

Microsoft Teams管理者は、ユーザーごとの通話分析を使用して、**個々** のユーザーの通話品質と接続の問題Teamsトラブルシューティングできます。 通話分析を最大限に活用するには、次を設定します。
  
- ヘルプデスク エージェントなどのユーザーに特殊なサポート ロールを割り当てて、ユーザーの通話分析を表示できるようにします。 これらのサポート ロールは、Teams管理センターの残りの部分にはアクセスできません。 
    
- .tsv または.csvデータ ファイルをアップロードして、ビルド、サイト、テナントの情報をユーザーごとの通話分析に追加します。
    
ユーザーごとの通話分析の使用を開始する準備ができたら、「ユーザー [ごとの通話分析を使用して通話品質の低下をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)」を参照してください。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>サポートスタッフとヘルプデスク スタッフにアクセス許可を付与する

Teams管理者は、すべてのユーザーの分析情報を呼び出すフル アクセス権を持っています。 サポート スタッフとヘルプデスク エージェントに割り当てることができる特殊なAzure Active Directory ロールをいくつか作成しました。これにより、ユーザーごとの通話分析にアクセスすることもできます (他のTeams管理センターにアクセスする必要はありません)。 **Teams通信サポート スペシャリスト** ロールを、ユーザーごとの通話分析 (階層 1 のサポート) の限られたビューを持つ必要があるユーザーに割り当てます。 **Teams通信サポート エンジニア** ロールを、ユーザーごとの通話分析 (階層 2 のサポート) へのフル アクセスが必要なユーザーに割り当てます。 どちらのロールも、Teams管理センターの残りの部分にアクセスすることはできません。

これらの各ロールの動作については、「[各Teamsサポート ロールは何を行いますか](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?」を参照してください。

Teams管理者ロールの詳細については、「[Teams管理者ロールを使用してTeamsを管理する」を](using-admin-roles.md)参照してください。 Azure Active Directoryで管理者ロールを割り当てる方法については、「[Azure Active Directoryでのロールの表示と割り当て](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。

Azure Active Directoryで管理ロールを割り当てる方法については、「Azure Active Directory[でのロールの表示と割り当て](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>.tsv または.csv ファイルをアップロードして、建物、サイト、テナントの情報を追加する

.csvファイルまたは .tsv ファイルをアップロードすることで、建物、サイト、テナントの情報をユーザーごとの通話分析に追加できます。 この情報をすべて使用して、通話分析は IP アドレスを物理的な場所にマップできます。 管理者とヘルプデスク エージェントは、この情報を使用して、通話の問題の傾向を特定するのに役立ちます。 たとえば、同じ建物のユーザーが同様の通話品質の問題を抱えているのはなぜですか? 

TeamsまたはSkype for Business管理者の場合は、既存のテナントを使用し、TeamsまたはSkype for Business通話品質ダッシュボード (CQD) からデータ ファイルを構築できます。 まず、CQD からファイルをダウンロードし、分析を呼び出すためにアップロードします。 

- 既存のデータ ファイルをダウンロードするには、**Microsoft Teams admin** **centerAnalytics** >  & reportsCall  > **Quality Dashboard** > **アップロードに移動します**。 [ **マイ アップロード** ] ボックスの一覧で、目的のファイルの横にある [ **ダウンロード** ] をクリックします。 

- 新しいファイルをアップロードするには、「 [レポート ラベルの追加と更新」を](/microsoftteams/learn-more-about-site-upload)参照してください。
  
.tsv または .csv ファイルを最初から作成する場合は、[テナントとデータの構築アップロード](CQD-upload-tenant-building-data.md)参照してください。
  
## <a name="related-topics"></a>関連項目

[ユーザーごとの通話分析を使用して通話品質の低下をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
