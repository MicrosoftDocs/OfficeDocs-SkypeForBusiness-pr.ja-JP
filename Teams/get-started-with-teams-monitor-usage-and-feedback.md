---
title: Microsoft Teams での使用状況とフィードバックを監視する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 03/20/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dstrome
description: ユーザーが Microsoft Teams をどのように使用しているかについて確認する場合や、ユーザーのエクスペリエンスに関するフィードバックを収集する場合に使用可能なレポート オプションについて説明します。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd877c88182046382a7502f59f6574c1c9cc0561
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030493"
---
# <a name="monitor-usage-and-feedback-in-microsoft-teams"></a>Microsoft Teams での使用状況とフィードバックを監視する
ユーザーがどのように Teams を使用していているか、また Teams に関するユーザーのエクスペリエンスはどのようなものかを知ることは重要です。 使用状況レポートは、使用パターンを正しく理解するために役立ちます。また、ユーザーのフィードバックと併用することで、広範な展開の情報を確認し、トレーニングとコミュニケーションの取り組みに関する優先順位を決定するための見識が得られます。

## <a name="monitor-usage"></a>使用状況の監視
最初のチームのセットについては、新たに出現する傾向を理解するために 1 週間に 2 回はレポートを確認するようにしてください。 

たとえば、Teams のモバイル クライアントを使用しているユーザーが、それほど多くいないことが使用状況レポートに示されているとします。 これは、ユーザーがクライアントのインストール方法を理解していないことを示している可能性があります。 チャネルに詳しいインストールの手順を投稿することで、広範なクライアントの使用を推進できるでしょう。 また、ユーザーが主にプライベート チャットのために Teams を使用していることを使用状況レポートが示しているとします。 この例では、ユーザーは最初にセットアップしたチームとチャネル以外でチャットしているため、チームのシナリオの再検討が必要になることがあります。 

次に、Teams の使用状況を確認するレポートの取得方法を示します。 

### <a name="teams-analytics--reports-microsoft-teams-admin-center"></a>Teams の分析とレポート (Microsoft Teams 管理センター)

Microsoft Teams 管理センターでの Teams のレポートにより、Teams が組織内でどのように使用されているかについての見識が得られます。 このレポートを使用して組織全体の Teams の使用状況、ユーザー アクティビティ、およびデバイスの使用状況について調べます。 

このようなレポートを表示するには、 Microsoft 365 または Office 365 の全体管理者、Teams のサービス管理者、または Skype for Business の管理者であることが必要です。Microsoft Teams 管理センターに移動して、左側のナビゲーションにある **[分析およびレポート]** を選択し、 **[レポート]** から実行するレポートを選択します。

- **Teams の使用状況レポート** : このレポートには、Teams の使用状況アクティビティの概要が示されます。アクティブなユーザーとチャネルの合計数、アクティブなユーザー数とチャネル数、ゲスト数、および各チームのメッセージ数も示されます。 

    ![Teams の使用状況レポートのスクリーンショット](media/teams-reports-teams-usage.png "Microsoft Teams 管理センターの Teams の使用状況レポートのスクリーンショット")     
- **Teams のユーザー アクティビティ レポート** : このレポートでは、1 対 1 の通話、チャネルのメッセージ、およびプライベート チャットのメッセージで通信したユーザー数など、ユーザーが関与したアクティビティの種類についての見識が得られます。 

    ![Teams のユーザー アクティビティ レポートのスクリーンショット](media/teams-reports-user-activity.png "Microsoft Teams 管理センターの Teams のユーザー アクティビティ レポートのスクリーンショット") 
`
- **Teams のデバイス使用状況レポート** : このレポートには、ユーザーがどのように Teams に接続しているかが示されます。外出先で自分のモバイル デバイスから Teams を使用したユーザーの数も示されます。 

    ![Teams のデバイス使用状況レポートのスクリーンショット](media/teams-reports-device-usage.png "Microsoft Teams 管理センターの Teams のデバイス使用状況レポートのスクリーンショット")

詳細については、「[Teams の分析とレポート](teams-analytics-and-reports/teams-reporting-reference.md)」を参照してください。 

### <a name="teams-activity-reports-microsoft-365-admin-center"></a>(Microsoft 365 管理センターでの) Teams のアクティビティ レポート
Teams のアクティビティは、 Microsoft 365 管理センターから利用可能なレポートで確認することもできます。 これに該当するレポートは、Microsoft 365 管理センターの Microsoft 365 レポートに含まれていて、ユーザー アクティビティとデバイス使用状況に関する情報が示されます。 

このレポートを表示するには、 Microsoft 365 管理センターに移動して **[レポート]** > **[使用状況]** をクリックします。 **[レポートの選択]** で、 **[Microsoft Teams]** をクリックします。 ここから、表示するレポートを選択します。

詳細については、「[Teams のアクティビティ レポートを使用する](teams-activity-reports.md)」を参照してください。

### <a name="microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析

Power BI の Microsoft 365 利用状況分析を使用すると、Teams などの Microsoft 365 または Office 365 製品とサービスの使用状況データを表示および分析できます。 Microsoft 365 利用状況分析は、事前に作成された 1 つのダッシュボードと事前に作成された複数のレポートが含まれているコンテンツ パックです。 それぞれのレポートで特定の使用状況のデータと見識が得られます。 このコンテンツ パックに接続するには、Power BI が必要になります。また、 Microsoft 365、Office 365 の全体管理者、またはレポート閲覧者であることが必要です。 まだ Power BI がない場合は、[無料の Power BI サービスにサイン アップ](https://powerbi.microsoft.com)してください。 

詳細については、「[Microsoft 365 利用状況分析](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)」を参照してください。 

## <a name="gather-feedback"></a>フィードバックの収集
新しい共同作業エクスペリエンスの導入は、ユーザーの行動を変更するということです。 その変更を可能にするには、トレーニング、奨励、および肯定的な例が必要です。 Teams への移行時にはユーザーに発言権があることと、ユーザーの経験をオープンに共有できるようにすることが重要です。 「Get to know Teams」チームの [Feedback] チャネルの使用をお勧めします。このチャネルは、ユーザーから Teams での経験に関するフィードバックを収集して処理するために作成したものです。 

## <a name="next-steps"></a>次のステップ
「[Teams の組織全体の展開を計画するためのリソースを取得する](get-started-with-teams-resources-for-org-wide-rollout.md)」に移動します。
