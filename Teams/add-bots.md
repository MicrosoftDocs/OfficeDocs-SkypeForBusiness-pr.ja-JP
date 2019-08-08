---
title: Microsoft Teams でプライベートのチャットやチャネルのボットを追加する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: 個人チャット、グループチャット、チャネル用に Microsoft Teams でボットを追加する方法と、個人チャット、グループチャット、チャネル用のボットをアップロードする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f5f031b01837980897f2c1f8ad5d306e056257b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239058"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>Microsoft Teams でパーソナルチャット、グループチャット、チャネルのボットを追加する
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

ボットとは、クエリに応答したり、ユーザーが興味を持っている詳細や常に情報を得ていたい詳細について更新や通知を行う自動プログラムのことです。 ボットは、ユーザーが Microsoft Teams でのチャットの会話を通じて、タスク管理、スケジュール、ポーリングなどのクラウドサービスを操作できるようにします。 Teams のボットは、 [Microsoft ボットのフレームワーク](https://go.microsoft.com/fwlink/?linkid=854370)上に構築されています。 このフレームワークを使って開発されたボットは、Teams で簡単に有効にすることができます。 詳細については、[組織のMicrosoft Teams 設定の管理](enable-features-office-365.md)を参照してください。

現時点では、チームは、個人チャット、グループチャット、チーム内のチャネルでボットをサポートしています。 管理者は、Office 365 テナント内でボットの使用を許可または禁止するかどうかを制御できます。<span id="_T-Bot" class="anchor"></span>

コミュニティによって開発されたボットは Teams 内で活用できます。 ボットの機能とカスタムアプリ (サイドローディングとも呼ばれます) をアップロードする機能は、カスタムボットが機能するためにテナントレベルで有効になっている必要があります。 ボットは、個人チャット、グループチャット、チャネルで使用できます。 チャネルの場合、チーム所有者またはメンバーがボットを追加できます。

詳細については、「[アプリとサービス](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)」を参照してください。

> [!IMPORTANT]
> テスト以外の理由で、[GUID] にボットを追加することはお勧めしません。 これにより、ボットの機能が大幅に制限されます。 製品使用中のボットは、アプリの一部として Teams に追加する必要があります。 「[ボットを作成](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create)して、 [Microsoft Teams のボットをテストしてデバッグする](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)」を参照してください。

<a name="create-custom-bots-for-microsoft-teams"></a>Microsoft Teams のカスタム ボットの作成
--------------------------------------

Microsoft ボットフレームワークを使用して、LOB アプリケーションに統合されるボットを簡単に作成することができます。 独自のボットを開発して公開する方法については、「 [Microsoft Teams のボットの作成とテスト](https://go.microsoft.com/fwlink/?linkid=854371)」のガイダンスを参照してください。

ボットを作成してボットのフレームワークに登録すると、それを公開することを選択できます。 公開しない場合、ボットはプライベートのままになります。 ボットを使う前にログインするようユーザーに要求することもできます。 ログインを要求することで、ボットのアプリケーション ID が既知のものになった場合でも組織の従業員のみがそのボットにアクセスできるようにできます。 ボットを使った Active Directory でユーザー認証を実行する方法のコード例については、GitHub の[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) をご覧ください。

ボットはチームへの展開前に [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) を使用してテストできます。

<a name="upload-your-bot-for-personal-chat"></a>お客様のボットをアップロードする
---------------------------------------

1. ボットを作成したら、開発したボットの**アプリケーション設定**に移動し、[アプリの**設定**] の [ **microsoft appid** ] 設定の値をコピーします。![ボット用のアプリケーション設定ページのスクリーンショット](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  Teams の**チャット**ウィンドウで、[**チャットの追加] アイコン**を選択します。 [**宛先**] に、ボットの**Microsoft アプリ ID**を貼り付けます。 ![Microsoft アプリ ID が強調表示されたチャットウィンドウのスクリーンショット](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. アプリ ID は**ボット名**に解決され、そのボットとのチャット会話を開始できます。

<a name="upload-your-bot-for-group-chats-or-channels"></a>グループチャットまたはチャネル用のボットをアップロードする
-----------------------------------

ボットを同僚と共有する場合は、次のようにして、グループチャットやさまざまなチームのチャンネルに追加します。

1. [ボットのアプリパッケージを作成](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)したら、Teams を開き、ボットをアップロードするチームを参照します。
2. **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)** のアプリを Teams に追加します。
3. App Studio で、[マニフェスト**** エディター] タブの![スクリーンショットを選択します。](media/Adding_Bot_To_Teams.png)
4. ボットを追加するには、[機能] でボットを選択して、既存のボットを追加します。 次に、既存のボットを選択するか、既存のボットの Id を入力します。
![既に作成したボットの選択を表示します。](media/Select_Existing_Bot.png)
5. アプリ パッケージの場所を参照、選択し、**開く**を選択します。
6. ボットの名前を選択します。 ([範囲] セクションの下にある [**グループチャット**] または [**チーム**] チェックボックスを必ずオンにしてください)。
7. [**テストと配布**] を選択します。
8. ボットを接続するグループチャットまたはチームを選択します。

    お客様のボットは、Teams のグループチャットまたはチームで利用できます。
