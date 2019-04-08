---
title: Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: プライベート チャットとチャネル用に Microsoft Teams にボットを追加する方法、カスタム ボットを作成する方法、プライベート チャット用に独自のボットをサイド ロードする方法について紹介します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3dfaabcbb2099f0b677e03b58ce79b5a7fca3237
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458805"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

ボットは、検索要求に応答したり、ユーザーが興味のある情報や最新情報の更新や通知を提供する自動プログラムです。ボットによって、ユーザーは、Microsoft Teams のチャット会話を介して、タスク マネージメント、スケジューリング、ポーリングなどのクラウド サービスと情報交換する事ができます。Microsoft Teams のボットは [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) に組み込まれています。このフレームワークにより作成されたボットは Microsoft Teams で簡単に有効にできます。詳細については「[Office 365 の組織で Microsoft Teams の機能を管理する](enable-features-office-365.md)」をご覧ください。

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

1. ボットを作成したら、作成したボットの **アプリケーションの設定** に移動し、**アプリの設定**の **MicrosoftAppId**設定の値をコピーします。![強制表示された Microsoft アプリ ID のボットのアプリケーション設定ページのスクリーンショット](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  Microsoft Teams の [**チャット**] ウィンドウで [**Add chat icon (チャット アイコンの追加)**] を選択します。 [**To: (相手)**] にはボットの [**Microsoft App ID (Microsoft アプリ ID)**] を貼り付けます。 ![チャットを追加するアイコンと、[Microsoft App ID (Microsoft アプリ ID)] が強調表示された [To (相手)] 行が含まれているチャット ウィンドウのスクリーンショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  アプリ ID は [**ボット名**] になります。この手順の実行後にボットとのチャット会話を開始できます。

<a name="side-load-your-bot-for-channels"></a>チャンネルのボットをサイド ローディングする
-----------------------------------

ここでは、ボットを同僚と共有する場合の、さまざまなチームのチャネルにボットを追加する方法を紹介します。

1. [ボットのアプリ パッケージを作成](https://docs.microsoft.com/ja-JP/microsoftteams/platform/concepts/apps/apps-upload)したら、Teams を開き、サイド ローディングするボットのチームを参照します。
2. チーム名の横にある**詳細** (...) を選択します。
3. **チームを管理する** を選択し、**アプリ** タブを選択します。
4. スクリーンの右下の **カスタム アプリをアップロードする**を選択します。
5. アプリ パッケージの場所を参照、選択し、**開く**を選択します。
