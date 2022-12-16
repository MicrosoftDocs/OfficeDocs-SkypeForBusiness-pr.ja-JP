---
title: Microsoft Teams の使用状況レポート
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 自分の組織での Teams のアクティビティの概要を把握するために、Microsoft Teams 管理センターにある Teams の使用状況レポートを、どのように使用するかについて説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ef5011ebbfbcbb62332c1fd9a43b19ce2b25b0ff
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436693"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams の使用状況レポート

The Teams usage report in the Microsoft Teams admin center gives you an overview of the usage activity in Teams, including the number of active users and channels, so you can quickly see how many users across your organization are using Teams to communicate and collaborate. You can view usage information for  teams, including the number of active users and channels, guests, and messages in each team.

内部ユーザーと外部ユーザーに関する情報が追加されたので、チーム内の内部および外部 [の共有チャネル](/Teams/shared-channels.md) 内のコラボレーションを測定できるようになりました。 たとえば、アクティブな共有チャネルやチーム内の外部アクティブ ユーザーなどのメトリックは、管理者がチーム内の共有チャネル間のコラボレーションを測定するのに役立ちます。

## <a name="view-the-usage-report"></a>使用状況レポートを表示する

Teams 管理センターでレポートを表示するには、グローバル管理者、グローバル閲覧者およびレポート閲覧者、または Teams サービス管理者である必要があります。 「[Teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 **[レポートの表示]** タブの **[レポート]** で、**[Teams ユーザーの利用状況]** を選択します。
2. **[日付の範囲]** で範囲を選択し、**[レポートの実行]** をクリックします。

    ![Teams 管理センターの Teams 使用状況レポートと吹き出しのスクリーンショット。](../media/teams-reports-teams-usage-with-callouts2.png "Teams 管理センターの Teams 使用状況レポートの吹き出しつきスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |Teams 利用状況レポートは、過去 7 日間、30 日間、90 日間、180 日間の傾向を確認できます。 |
|**2**   |各レポートには、このレポートが生成された日付が表示されます。 レポートには、通常、アクティビティの時間から 24 時間から 48 時間の待機時間が反映されます。 |
|**3**   |<ul><li>グラフ上の X 軸はこのレポートで選択した日付範囲です。</li> <li> Y 軸はアクティブな項目またはアクティビティの数です。</li> </ul>特定の日付の項目またはアクティビティを示しているドットの上にマウス カーソルを合わせると、その特定の日付のその項目またはアクティビティのインスタンスの数を見ることができます。|
|**4**   |凡例の項目をクリックして、グラフに表示する情報をフィルター処理できます。 たとえば、[  **内部アクティブ ユーザー**]、[ **アクティブ なゲスト**]、[  **アクティブ なチャネル**]、[ **投稿]** などをクリックすると、それぞれに関連する情報のみが表示されます。 この選択を変更しても、表内の情報は変わりません。 |
|**5**   |表によって、チームごとの使用状況の内訳が表示されます。 <ul><li>**チーム名** はチームの表示名です。 チーム名をクリックして、Microsoft Teams 管理センターのチームの設定ページに移動できます。 </li> <li>**チーム ID** は、一意のチーム識別子です。 </li> <li>**型** は、チームがプライベート チームかパブリック チームかを指します。</li> <li>**内部アクティブ ユーザー** は、指定された期間内にそのチームでアクションを実行するゲストを含むアクティブ ユーザーの数です。 <br/>内部ユーザーとゲストは同じテナントに存在しますが、同じではありません。</li><li>**アクティブなゲスト** は、指定した期間内にそのチームでアクションを実行するゲストの数です。</li> <li>**外部アクティブ ユーザー** (新規) は、リソース内のそのチームでアクションを実行する外部組織のアクティブ ユーザー (チーム内の共有チャネルなど) の数です。 <br/> 外部ユーザーは、異なるテナントに独自の ID を持ち、ゲスト アカウントと同じではありません。</li><li>**アクティブ チャネル** は、指定した期間内に少なくとも 1 人のアクティブ ユーザーを持つチーム内のチャネルの数です。 これには、プライベート、パブリック、および共有チャネルが含まれます。 </li><li>**アクティブな共有チャネル** (新規) は、指定された期間内に少なくとも 1 人のアクティブな内部ユーザーまたは外部ユーザーを持つチーム内の共有チャネルの数です。 </li> <li>**開催された会議の合計** は、ユーザーが指定した期間中に開催したスケジュールされた 1 回の会議、定期的な会議、計画外の会議、および未分類の会議の合計です。 </li><li>**[投稿]** は、指定した期間内のチャネル内のすべての投稿メッセージの数です。</li> <li>**応答** は、指定された期間内のチャネル内のすべての応答メッセージの数です。</li> <li>**メンション** は、指定された期間内のメンションの総数です。</li><li>**リアクション** は、指定された期間内のメッセージに対するリアクションの総数です。</li><li>**[緊急メッセージ** ] は、指定した期間内のすべての緊急メッセージの数です。</li><li>**チャネル メッセージ** は、指定した期間中にチームのユーザーがチーム チャットに投稿した一意のメッセージの数です。</li> </li> </ul>チームが存在しなくなった場合、表内で名前は "--" と表示されることに注意してください。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**6**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**7**   |オフライン分析のためにレポートを CSV ファイルにエクスポートします。 [ **Excel にエクスポート** ] アイコンを選択すると、レポートがブラウザーにダウンロードされます。|
|**8** |上位のグラフで表される時系列データは、テナント全体に対して集計されたさまざまな使用状況メトリックを示します|
|**9** |下半分で表される表形式データは、チームごとに集計されたさまざまな使用状況メトリックを示しています|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]


## <a name="make-the-user-specific-data-anonymous"></a>ユーザー固有のデータを匿名にする

Teams ユーザー アクティビティ レポートのデータを匿名にするには、グローバル管理者である必要があります。 グローバル管理者は、表示名、グループ名、電子メール、AAD ID などの識別可能な情報 (MD5 ハッシュを使用) をレポートとそのエクスポートで非表示にすることができます。

1. Microsoft 365 管理センターで、[**設定** > **] [組織の設定]** に移動し、[**サービス**] タブの [**レポート**] を選択します。
    
2. [ **レポート]** を選択し、[ **すべてのレポートに隠されたユーザー、グループ、サイト名を表示** する] を選択します。 この設定は、Microsoft 365 管理センターの使用状況レポートと Teams 管理センターの両方に適用されます。
  
3. [ **変更の保存] を選択します**。

> [!NOTE]
> この設定を有効にすると、Teams ユーザー アクティビティ レポート、[Teams デバイス使用状況](device-usage-report.md)[レポート、および Teams](user-activity-report.md) [使用状況](teams-usage-report.md)レポートのユーザー、グループ、およびサイト名の情報が識別されなくなります。 2021 年 9 月 1 日から、この設定は、重要な情報を保護し、企業が地域のプライバシー法をサポートできるようにするための継続的な取り組みの一環として、すべてのユーザーに対して既定で有効になっています。 
>
>この設定は、Microsoft 365 管理センター、Microsoft Graph、Power BI の Microsoft 365 使用状況レポートにも適用されます。

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
