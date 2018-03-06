---
title: "Microsoft Teams でプライベートのチャットやチャネルのボットを追加する"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
description: "プライベート チャットとチャネル用に Microsoft Teams にボットを追加する方法、カスタム ボットを作成する方法、プライベート チャット用に独自のボットをサイド ロードする方法について紹介します。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d95f95e3c7db9ea257cf26761c41205eeacd131
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
==========================================================

ボットは、問い合わせに応答したり、興味のある情報や最新情報に関する更新および通知を提供する自動化されたプログラムです。ボットによって、ユーザーは、Microsoft Teams のチャット会話を介して、タスク管理、スケジューリング、ポーリングなどのクラウド サービスと相互にやり取りできます。Microsoft Teams のボットは [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) に基づいており、このフレームワークにより作成されたボットは Microsoft Teams で容易に有効にできます。詳細については「[Office 365 を使用する組織で Microsoft Teams の機能を有効にする](enable-features-office-365.md)」をご覧ください。

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

1.  ボットを作成した後、開発したボットの [**Bot Dashboard (ボットのダッシュボード)**] [ページ](https://go.microsoft.com/fwlink/?linkid=854374)に移動して、[**詳細**] で [**Microsoft App ID (Microsoft アプリ ID)**] をコピーします。![[Microsoft App ID (Microsoft アプリ ID)] が強調表示された状態のボットの詳細ページのスクリーンショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png) 



2.  Microsoft Teams の [**チャット**] ウィンドウで [**Add chat icon (チャット アイコンの追加)**] を選択します。 [**To: (相手)**] にはボットの [**Microsoft App ID (Microsoft アプリ ID)**] を貼り付けます。 ![チャットを追加するアイコンと、[Microsoft App ID (Microsoft アプリ ID)] が強調表示された [To (相手)] 行が含まれているチャット ウィンドウのスクリーンショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  アプリ ID は [**ボット名**] になります。この手順の実行後にボットとのチャット会話を開始できます。
