---
title: "Microsoft Teams でプライベートのチャットやチャネルのボットを追加する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: tutorial
ms.prod: teams
description: "プライベート チャットとチャネル用に Microsoft Teams にボットを追加する方法、カスタム ボットを作成する方法、プライベート チャット用に独自のボットをサイド ロードする方法について紹介します。"
ms.openlocfilehash: a93e2b27c350de043fe1d1af553a3d2d727db0fd
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
==========================================================

ボットは、問い合わせに応答したり、興味のある情報や最新情報に関する更新および通知を提供する自動化されたプログラムです。ボットによって、ユーザーは、Microsoft Teams のチャット会話を介して、タスク管理、スケジューリング、ポーリングなどのクラウド サービスと相互にやり取りできます。Microsoft Teams のボットは [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) に基づいており、このフレームワークにより作成されたボットは Microsoft Teams で容易に有効にできます。

現在、Microsoft Teams は、チーム内のプライベート チャットとチャネルにおけるボットをサポートしています。管理者は、Office 365 テナント内でのボットの使用可否を管理できます。<span id="_T-Bot" class="anchor"></span>

コミュニティにより作成されて利用可能となったボットは、Microsoft Teams 内で利用できます。カスタム ボットを機能させるには、ボットの機能とサイド ローディングをテナント レベルで有効にする必要があります。ボットはプライベート チャットまたはチャネルにおいて使用できます。チャネルの場合、チーム所有者またはメンバーがボットを追加できます。

<a name="add-bots-for-private-chat-and-channels"></a>プライベート チャットとチャネル用ボットの追加
--------------------------------------

プライベート チャットとチャネル用のボットを統合する場合、次に示す 2 つの方法があります。

1.  公開されている**プライベート チャット**または**チャネル**用のボットをインストールする。(これが第 1 のオプションとなります。)

2.  または、ボットを検索するには、[**チャット**] に移動して、[**連絡先**] を検索して、[**アプリを検出**] をクリックします。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  以下に示すとおり、会話をしたい**ボット**を選択します。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  選択したら、ボットに**権限**を与え、**ボットをプライベート チャットで**使用したいかどうかを選択するか、ボットを使用する**チーム**を選択します。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  ボットをチームのチャネル内で使用する場合は、[**View Team and Bots (チームとボットを表示)**] をクリックするだけです。このようにすることで、その他のボットを見つけることができます。

6.  ボットはいつでもチームから削除できます。この場合は、[**View Team and Bots (チームとボットを表示)**] をクリックして、すべてのボットを表示してから、目的のボットを [**削除**] します。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a>Microsoft Teams のカスタム ボットの作成
--------------------------------------

Microsoft ボット フレームワークを使用して、LOB アプリケーションに統合されるボットを簡単に作成できます。独自のボットを作成および公開する方法については、[Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) のガイダンスを参照してください。

ボットを作成してボットのフレームワークに登録すると、それを公開するかどうかを選択することができます。公開しない場合、ボットはプライベートのままになります。ボットを使う前にログインするようユーザーに要求することもできます。ログインを要求することで、ボットのアプリケーション ID が既知のものになった場合でも組織の従業員のみがそのボットにアクセスできるようにできます。ボットを使った Active Directory でユーザー認証を実行する方法のコード例については、GitHub の「[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)」をご覧ください。

ボットはチームへの展開前に [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) を使用してテストできます。

<a name="side-load-your-own-bot-for-private-chat"></a>プライベート チャット用の独自のボットのサイド ロード
---------------------------------------

1.  ボットを作成したら、作成したボットの [**Bot Dashboard (ボットのダッシュボード)**] [ページ](https://go.microsoft.com/fwlink/?linkid=854374)に移動して、[**詳細**] で [**Microsoft App ID (Microsoft アプリ ID)**] をコピーします。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  Microsoft Teams の [**チャット**] ウィンドウで [**Add chat icon (チャット アイコンの追加)**] を選択します。[**To: (相手)**] にはボットの [**Microsoft App ID (Microsoft アプリ ID)**] を貼り付けます。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  アプリ ID は [**ボット名**] になります。この手順の実行後にボットとのチャット会話を開始できます。
