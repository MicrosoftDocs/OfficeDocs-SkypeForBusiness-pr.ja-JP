---
title: ユーザーの通話分析を設定Microsoft Teams
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
ms.openlocfilehash: c19a5b05027bd9d2aa0fd8d3a6c8599c30ae54cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597571"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>ユーザーの通話分析を設定Microsoft Teams

管理者Microsoft Teams、ユーザーごとの呼び出し分析を使用して、個々のユーザーの通話品質Teams接続の問題のトラブルシューティング **を行います**。 通話分析をフルに活用するには、次の設定を行います。
  
- ヘルプデスク エージェントなどのユーザーに特殊なサポート ロールを割り当て、ユーザーの通話分析を表示します。 これらのサポート ロールは、管理センターの残りのTeamsアクセスできない。 
    
- .tsv または .csv データ ファイルをアップロードして、ビル、サイト、テナントの情報をユーザーごとの呼び出し分析に追加します。
    
ユーザーごとの呼び出し分析の使用を開始する準備ができたら、「ユーザーごとの通話分析を使用して低品質の通話のトラブルシューティングを行う」 [を参照してください](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>サポートとヘルプデスクのスタッフにアクセス許可を付与する

管理者はTeams、すべてのユーザーの分析情報を呼び出すフル アクセス権を持っています。 サポート スタッフおよびヘルプデスク エージェントに割り当て可能な特殊な Azure Active Directory ロールを作成しました。このロールは、ユーザーごとの通話分析にもアクセスできます (Teams 管理センターの残りの部分にはアクセスできません)。 ユーザーごとの **通話Teamsビュー** を限定する必要があるユーザー (階層 1 のサポート) に、コミュニケーション サポート スペシャリスト ロールを割り当てる。 ユーザーごとの **通話Teamsフル** アクセスが必要なユーザーに、通信サポート エンジニア ロールを割り当てる (階層 2 のサポート)。 どちらのロールも、管理センターの他のTeamsアクセス権を持つ必要があります。

これらの各ロールについて詳しくは、「各ロールのサポート ロール[Teamsについて」をご覧ください](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)。

管理者ロールの詳細についてはTeams管理者ロールを使用[した](using-admin-roles.md)管理Teamsを参照Teams。 アカウントで管理者ロールを割り当てる方法については、「Azure Active Directory でロールを表示して割り当[てる」をAzure Active Directory。](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

管理ロールを管理ロールに割り当てる方法については、「Azure Active Directory でロールを表示して割り当てる[」をAzure Active Directory。](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>アップロード.tsv または .csv ファイルを作成して、ビル、サイト、テナントの情報を追加する

ユーザーごとの通話分析に建物、サイト、テナントの情報を追加するには、.csv または .tsv ファイルをアップロードします。 このすべての情報により、通話分析は IP アドレスを物理的な場所にマップできます。 管理者とヘルプデスク エージェントは、この情報を使用して通話の問題の傾向を特定できます。 たとえば、同じビル内のユーザーが同様の通話品質の問題を抱えている理由は何ですか。 

Teams または Skype for Business 管理者の場合は、既存のテナントを使用し、Teams または Skype for Business 通話品質ダッシュボード (CQD) からデータ ファイルを作成できます。 最初に、CQD からファイルをダウンロードし、それをアップロードして分析を呼び出します。 

- 既存のデータ ファイルをダウンロードするには、管理センターの [通話品質ダッシュボード] Microsoft Teams **に移動アップロード**  >    >  **します**。 [マイ **アップロード] の一覧** で、必要な **ファイルの** 横にある [ダウンロード] をクリックします。 

- 新しいファイルをアップロードするには、[管理センターの場所] Microsoft Teamsに移動し、[場所データ] または [場所アップロードを置き換える]  >  **を選択します**。 
  
.tsv または .csv ファイルを最初から作成する場合は、テナントのアップロードデータの構築[に関するページを参照してください](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>関連トピック

[ユーザーごとの通話分析を使用して低品質の通話のトラブルシューティングを行う](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)