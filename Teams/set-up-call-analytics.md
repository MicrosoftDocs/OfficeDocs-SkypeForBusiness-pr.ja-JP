---
title: Microsoft Teams の通話分析を設定する
author: CarolynRowe
ms.author: crowe
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
description: Microsoft Teams の通話品質の問題を特定してトラブルシューティングするために、ユーザーごとの通話分析を設定します。
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789942"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Microsoft Teams の通話分析を設定する

Microsoft Teams 管理者は、ユーザーごとの通話分析を使用して、 **個々のユーザー** の Teams 通話の品質と接続に関する問題のトラブルシューティングを行うことができます。 通話分析を最大限に活用するには、次を設定します。
  
- ヘルプデスク エージェントなどのユーザーに特殊なサポート ロールを割り当てて、ユーザーの通話分析を表示できるようにします。 これらのサポート ロールは、Teams 管理センターの残りの部分にはアクセスできません。 
    
- .tsv または.csvデータ ファイルをアップロードして、ビルド、サイト、テナントの情報をユーザーごとの通話分析に追加します。
    
ユーザーごとの通話分析の使用を開始する準備ができたら、「ユーザー [ごとの通話分析を使用して通話品質の低下をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)」を参照してください。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>サポートスタッフとヘルプデスク スタッフにアクセス許可を付与する

Teams 管理者は、すべてのユーザーの分析情報を呼び出すフル アクセス権を持っています。 サポート スタッフとヘルプデスク エージェントに割り当てることができる特殊な Azure Active Directory ロールをいくつか作成しました。これにより、ユーザーごとの通話分析にアクセスすることもできます (Teams 管理センターの残りの部分にアクセスする必要はありません)。 **Teams 通信サポートスペシャリスト** ロールを、ユーザーごとの通話分析 (階層 1 のサポート) の限られたビューを持つ必要があるユーザーに割り当てます。 **Teams 通信サポート エンジニア** ロールを、ユーザーごとの通話分析へのフル アクセスが必要なユーザーに割り当てます (階層 2 のサポート)。 どちらのロールも、Teams 管理センターの残りの部分にアクセスすることはできません。

これらの各ロールの動作については、「 [各 Teams サポート ロールは何をしますか](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Teams 管理者ロールの詳細については、「 [Teams 管理者ロールを使用して Teams を管理する」を参照してください](using-admin-roles.md)。 Azure Active Directory で管理者ロールを割り当てる方法については、「Azure Active Directory での [ロールの表示と割り当て」を](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)参照してください。

Azure Active Directory で管理ロールを割り当てる方法については、「Azure Active Directory [でのロールの表示と割り当て」を](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)参照してください。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>.tsv または.csv ファイルをアップロードして、建物、サイト、テナントの情報を追加する

.csvファイルまたは .tsv ファイルをアップロードすることで、建物、サイト、テナントの情報をユーザーごとの通話分析に追加できます。 この情報をすべて使用して、通話分析は IP アドレスを物理的な場所にマップできます。 管理者とヘルプデスク エージェントは、この情報を使用して、通話の問題の傾向を特定するのに役立ちます。 たとえば、同じ建物のユーザーが同様の通話品質の問題を抱えているのはなぜですか? 

Teams またはSkype for Business管理者の場合は、既存のテナントを使用し、Teams または Skype for Business通話品質ダッシュボード (CQD) からデータ ファイルを構築できます。 まず、CQD からファイルをダウンロードし、分析を呼び出すためにアップロードします。 

- 既存のデータ ファイルをダウンロードするには、 **Microsoft Teams 管理センター** > **の Analytics &レポート** > **の通話品質ダッシュボード** > **のアップロードにアクセスします**。 [ **マイ アップロード** ] ボックスの一覧で、目的のファイルの横にある [ **ダウンロード** ] をクリックします。 

- 新しいファイルをアップロードするには、「 [レポート ラベルの追加と更新」を](/microsoftteams/learn-more-about-site-upload)参照してください。
  
.tsv または .csv ファイルを最初から作成する場合は、「 [テナントのアップロードとデータの構築](CQD-upload-tenant-building-data.md)」を参照してください。
  
## <a name="related-topics"></a>関連項目

[ユーザーごとの通話分析を使用して通話品質の低下をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
