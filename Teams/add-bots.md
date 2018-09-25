---
title: Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: lucarras
description: プライベート チャットとチャネル用に Microsoft Teams にボットを追加する方法、カスタム ボットを作成する方法、プライベート チャット用に独自のボットをサイド ロードする方法について紹介します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ff6cf5af3a1a2129ee22ae0ff51ac4216ccaefe
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013362"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

ボットは、クエリに応答したり、更新情報を提供する自動化されたプログラムとユーザーの詳細についての通知が興味深いかに関する情報を把握します。 ボットは、タスク管理、スケジュール、およびマイクロソフトのチームでのチャットの会話で、ポーリングのようなクラウド サービスと対話するようにします。 [マイクロソフト Bot のフレームワーク](https://go.microsoft.com/fwlink/?linkid=854370)では、マイクロソフト チームの bot が構築されます。 このフレームワークを使用して開発されたボットは、マイクロソフトのチームを簡単に有効にできます。 詳細については、 [Office 365 の組織での Microsoft チームの管理機能](enable-features-office-365.md)を参照してください。

現在、Microsoft Teams は、チーム内のプライベート チャットとチャネルにおけるボットをサポートしています。管理者は、Office 365 テナント内でのボットの使用可否を管理できます。<span id="_T-Bot" class="anchor"></span>

コミュニティにより開発されたボットは、Microsoft Teams 内で利用できます。 ボットを機能させるには、ボットの機能とサイド ローディングをテナント レベルで有効にする必要があります。 ボットはプライベート チャットまたはチャネルにおいて使用できます。 チャネルの場合、チーム所有者またはメンバーがボットを追加できます。

詳細については、[アプリとサービス](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)の「ボットの使用」セクションを参照してください。 




<a name="create-custom-bots-for-microsoft-teams"></a>Microsoft Teams のカスタム ボットの作成
--------------------------------------

Microsoft ボット フレームワークを使用して、LOB アプリケーションに統合されるボットを簡単に作成できます。独自のボットを作成および公開する方法については、[Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) のガイダンスを参照してください。

ボットを作成してボットのフレームワークに登録すると、それを公開することを選択できます。 公開しない場合、ボットはプライベートのままになります。 ボットを使う前にログインするようユーザーに要求することもできます。 ログインを要求することで、ボットのアプリケーション ID が既知のものになった場合でも組織の従業員のみがそのボットにアクセスできるようにできます。 ボットを使った Active Directory でユーザー認証を実行する方法のコード例については、GitHub の[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) をご覧ください。

ボットはチームへの展開前に [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) を使用してテストできます。

<a name="side-load-your-own-bot-for-private-chat"></a>プライベート チャット用の独自のボットのサイド ロード
---------------------------------------

1. Bot を作成して、ボットを開発した、し、[**アプリケーションの設定**の**アプリケーションの設定**を**MicrosoftAppId**の設定の値をコピーします。![の bot が強調表示されている Microsoft アプリケーションの ID を持つアプリケーションの設定のスクリーン ショットのページです。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  Microsoft Teams の [**チャット**] ウィンドウで [**Add chat icon (チャット アイコンの追加)**] を選択します。 [**To: (相手)**] にはボットの [**Microsoft App ID (Microsoft アプリ ID)**] を貼り付けます。 ![チャットを追加するアイコンと、[Microsoft App ID (Microsoft アプリ ID)] が強調表示された [To (相手)] 行が含まれているチャット ウィンドウのスクリーンショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  アプリ ID は [**ボット名**] になります。この手順の実行後にボットとのチャット会話を開始できます。
