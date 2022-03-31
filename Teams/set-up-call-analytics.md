---
title: 通話分析を設定する Microsoft Teams
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
description: ユーザーごとの通話分析を設定して、通話品質の問題を特定Microsoft Teamsトラブルシューティングします。
ms.openlocfilehash: be93a24f7d18e5b347c6375622ca47c3bdaeae26
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556478"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>通話分析を設定する Microsoft Teams

管理者はMicrosoft Teamsユーザーごとの通話分析を使用して、個々のユーザーの通話品質Teams接続に関する問題のトラブルシューティング **を行います**。 通話分析をフルに活用するには、次の設定を行います。
  
- ヘルプデスク エージェントなどのユーザーに特殊なサポート ロールを割り当て、ユーザーの通話分析を表示します。 これらのサポート ロールは、管理センターの残りのTeamsアクセスできない。 
    
- .tsv または .csv データ ファイルをアップロードして、ビル、サイト、テナントの情報をユーザーごとの呼び出し分析に追加します。
    
ユーザーごとの通話分析の使用を開始する準備ができたら、「ユーザーごとの通話分析を使用して低品質の通話をトラブルシューティングする」 [を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>サポートとヘルプデスクのスタッフにアクセス許可を付与する

管理者はTeams、すべてのユーザーの分析情報を呼び出すフル アクセス権を持っています。 サポート スタッフおよびヘルプデスク エージェントに割り当て可能な特殊な Azure Active Directory ロールがいくつか作成されています。このロールは、ユーザーごとの通話分析にもアクセスできます (Teams 管理センターの残りの部分にはアクセスできません)。 ユーザーごとの **通話Teamsビュー** を限定する必要があるユーザーに、コミュニケーション サポート スペシャリスト ロールを割り当てる (第 1 層のサポート)。 ユーザーごとの **通話Teamsフル アクセス** が必要なユーザーに、コミュニケーション サポート エンジニア ロールを割り当てる (階層 2 のサポート)。 どちらのロールも、管理センターの他のTeamsアクセス権を持つ必要があります。

これらの各ロールについて詳しくは、「各ロールのサポート ロール[Teamsを参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)。

管理者ロールの詳細についてはTeams管理者ロールを使用した管理Teamsを[参照Teams](using-admin-roles.md)。 Azure Active Directory で管理者ロールを割り当てる方法については、「Azure Active Directory でのロールの表示と[割り当て」を参照してください](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

管理ロールをロールに割り当てる方法については、「Azure Active Directory でロールを表示して割り当てる[」をAzure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>アップロード.tsv または .csv ファイルを作成して、ビル、サイト、テナントの情報を追加する

ユーザーごとの呼び出し分析に建物、サイト、テナントの情報を追加するには、.csv または .tsv ファイルをアップロードします。 このすべての情報により、通話分析は IP アドレスを物理的な場所にマップできます。 管理者とヘルプデスク エージェントは、この情報を使用して通話の問題の傾向を特定できます。 たとえば、同じビル内のユーザーが同様の通話品質の問題を抱えている理由は何ですか。 

Teams または Skype for Business 管理者の場合は、既存のテナントを使用し、Teams または Skype for Business 通話品質ダッシュボード (CQD) からデータ ファイルを構築できます。 最初に、CQD からファイルをダウンロードし、それをアップロードして分析を呼び出します。 

- 既存のデータ ファイルをダウンロードするには、[管理センター]**Microsoft Teams** > [&**レポート** >  > ][すべての品質ダッシュボード]に移動 **アップロードします**。 [マイ **アップロード] の一覧** で、必要な **ファイルの** 横にある [ダウンロード] をクリックします。 

- 新しいファイルをアップロードするには、「レポート ラベルを追加 [および更新する」を参照してください](/microsoftteams/learn-more-about-site-upload)。
  
.tsv または .csv ファイルを最初から作成する場合は、テナントの作成とアップロード[に関するページを参照してください](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>関連項目

[ユーザーごとの通話分析を使用して低品質の通話のトラブルシューティングを行う](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
