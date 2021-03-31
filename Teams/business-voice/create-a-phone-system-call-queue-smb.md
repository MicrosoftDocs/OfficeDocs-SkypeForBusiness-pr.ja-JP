---
title: Microsoft Teams で通話キューを作成する - 小規模ビジネス向けチュートリアル
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Microsoft 365 Business Voice で通話キューを設定する方法について説明します。
ms.openlocfilehash: f4dcd38331812053df9d08c7e8417b6d8156d5af
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439732"
---
# <a name="create-a-call-queue---small-business-tutorial"></a>通話キューを作成する - 小規模ビジネス向けチュートリアル

通話キューは、組織内の特定の問題や質問に役立つユーザーに発信者をルーティングする方法を提供します。 通話はキュー内のユーザー (エージェントと呼ばれる) に一度に 1 つ配布 *されます*。 

通話キューには次の機能があります。

- あいさつメッセージ。

- ユーザーがキューで保留を待っている間の音楽。

- コール ルーティング - *First In、First Out* (FIRST Out )順序で- エージェントに。

- キュー オーバーフローとタイムアウトの処理オプション。

#### <a name="before-you-begin"></a>はじめに

電話システム [を取得する - 仮想ユーザー ライセンス](../teams-add-on-licensing/virtual-user.md) をまだ持ってない場合は、仮想ユーザー ライセンスを取得します。 セットアップする通話キューと自動応答ごとに 1 つ取得します。 これらのライセンスは無料なので、後でセットアップを変更する場合に備え、追加のライセンスを取得する方法をお勧めしています。

通話キュー内のエージェントがダイヤルアウトして顧客の通話を返す可能性がある場合は、通話エージェントの発信者番号をメインの電話番号または適切な自動応答の番号に設定します。 詳細 [については、「Microsoft Teams で発信者番号ポリシーを](../caller-id-policies.md) 管理する」を参照してください。

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a>通話キューをセットアップするには、次の手順に従います。

# <a name="step-1brcreate-a-team"></a>[手順 1 <br> チームを作成する](#tab/create-team)

通話キューを作成する場合は、個々のユーザーをキューに追加するか、既存のセキュリティ グループ、Microsoft 365 グループ、または Microsoft Teams チームを使用できます。 チーム チャネル [を使用することをお勧めします](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)。 これにより、キューのメンバーは互いにチャットしたり、アイデアを共有したり、顧客を支援するドキュメントや他のリソースを作成することができます。 また、チームは、発信者が数時間後にメッセージを残したり、キューが最大容量に達したりするためにボイス メールボックスを提供します。

チームを作成するには

1. まず、アプリ **の左側にある [Teams]** をクリックし、[参加] をクリックするか、チーム リストの下部にあるチームを作成します。

2. 次に、[ **チームの作成]** (最初のカード、左上隅) をクリックします。

3. [チーム **を一から作成] を選択します**。

4. 次に、パブリック チームとプライベート チームの選択を行います。 チームに **参加** することで、ユーザーが意図せずにキューに参加することを避けるために、通話キューにプライベートを使用することをお勧めします。

5. チームに名前を付け、オプションの説明を追加します。

6. 完了したら、[作成] をクリック **します**。

8. 通話キューに追加するユーザーの名前を入力し、[追加] をクリック **します**。

9. [**閉じる**] をクリックします。 チームに追加したユーザーには、チームのメンバーになれたというメールが送信され、チームがチーム リストに表示されます。

次に、通話キューで使用するチャネルを追加します。

チャネルを追加するには

1. Teams で、作成したチームを見つけ、[その他のオプション **]** (...) をクリックし、[チャネルの追加] **をクリックします**。

2. チャネルの名前と説明を入力し、[追加] をクリック **します**。

> [!div class="nextstepaction"]
> [手順 2 - リソース アカウントの>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[手順 2 <br> リソース アカウント](#tab/resource-account)

作成する各通話キューには、リソース アカウントが必要です。 これはユーザー アカウントに似ていますが、アカウントがユーザーではなく自動応答または通話キューに関連付けられている場合を除きます。 この手順では、アカウントを作成し *、Microsoft 365* 電話システム - 仮想ユーザー ライセンスを割り当て、それを使用して通話キューの作成を開始します。

### <a name="create-a-resource-account"></a>リソース アカウントを作成する

Teams 管理センターでリソース アカウントを作成できます。

1. Teams 管理センターで、組織全体の設定 **を** 展開し、[リソース アカウント] **をクリックします**。

2. **[追加]** をクリックします。

3. [リソース アカウント **の追加]** ウィンドウで、表示 **名**、ユーザー名を入力し、[リソース アカウントの種類] の **[** 通話キュー **] を選択します**。

    ![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add-cq.png)

4. **[保存]** をクリックします。

新しいアカウントがアカウントの一覧に表示されます。

![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>ライセンスを割り当てる

Microsoft *365* 電話システム - 仮想ユーザー ライセンスをリソース アカウントに割り当てる必要があります。

1. Microsoft 365 管理センターで、ライセンスを割り当てるリソース アカウントをクリックします。

2. [ライセンスと **アプリ] タブの** [ **ライセンス]** で **、[Microsoft 365 電話システム - 仮想ユーザー] を選択します**。

3. [変更を **保存] をクリックします**。

    ![Microsoft 365 管理センターのライセンスの割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a>呼び出しキューを作成する

次に、新しい通話キューの作成を開始し、リソース アカウントを割り当てします。

1. Teams 管理センターで、[音声] を **展開** し、[ **通話キュー**] をクリックして、[追加] をクリック **します**。

1. 通話キューの名前を入力します。 エージェントは、キューからの着信通話を受信すると、この名前を表示します。

2. [**アカウントの追加]** をクリックし、この通話キューで使用するリソース アカウントを検索し、[追加] をクリックして、[追加] をクリック **します**。

3. 言語を選択します。 この言語は、システム生成の音声プロンプトとボイスメール トランスクリプション (有効にした場合) に使用されます。

    ![リソース アカウントと言語設定のスクリーンショット](../media/call-queue-name-language.png)

4. 発信者がキューに入った場合に発信者に応答メッセージを再生する場合に指定します。 再生する応答メッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。

5. Teams は、キューで保留されている間、発信者に既定の音楽を提供します。 特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。

> [!NOTE]
> アップロードされた記録は 5 MB 以下にできます。
> Teams の通話キューで提供される既定の音楽には、組織が支払う料金は無料です。 

> [!div class="nextstepaction"]
> [手順 3 - コール エージェントが>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[手順 3 コール <br> エージェント](#tab/call-agents)

エージェントを通話キューに追加するには、先に作成したチームとチャネルにエージェントを追加します。

1. [チームの **選択] オプションを選択し** 、[チャネルの追加 **] をクリックします**。
2. 作成したチームの名前を入力して選択し、[追加] をクリック **します**。
3. キュー用に作成したチャネルを選択します。
3. [**適用**] をクリックします。

    ![通話キューのユーザーとグループの設定のスクリーンショット](../media/call-queue-users-groups.png)

> [!NOTE]
> 新しいユーザーがチームに追加された場合、最初の通話が到着するには最大 8 時間かかる場合があります。

> [!div class="nextstepaction"]
> [手順 4 - リソース アカウント>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[手順 4 通話 <br> ルーティング](#tab/call-routing)

使用する通話ルーティング方法を選択します。

1. 会議モード **を自動に****設定します**。

2. 使用する **ルーティング方法** を選択します。 これにより、エージェントがキューから通話を受信する順序が決定されます。 シリアル ルーティング **またはラウンド ロビン****をお勧めします**。 次のオプションから選択します。

    - **アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。 通話を受け取る最初の通話エージェントが通話を受け取る。

    - **シリアル ルーティングは** 、すべてのコール エージェントを 1 つ 1 つリングします。 エージェントが通話を却下するか、通話を受け取らない場合、通話は次のエージェントを呼び出し、エージェントが受け取されるか、または時間が切れるまですべてのエージェントを試します。

    - **ラウンド ロビンは** 、着信通話のルーティングのバランスを取り、各通話エージェントがキューから同じ数の通話を受け取ります。 これは、すべての通話エージェント間で同じ機会を確保するために、受信販売環境で望ましい場合があります。

    - **アイドル時間が** 最も長いエージェントに各呼び出しがルーティングされます。 (プレゼンス状態が 10 分以上離れたエージェントは含まれません)。

    ![電話会議モードとルーティング方法の設定のスクリーンショット](../media/call-queue-conference-mode-routing-method.png)

3. プレゼンス **ベースのルーティングを有効** にする。 これにより、プレゼンス状態が [使用可能] のエージェントに通話がルーティング **されます**。

4. エージェントが通話をオプトアウトすることを許可する場合に選択します。

5. エージェントの **通知時間を設定** して、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。

    ![ルーティング、オプトアウト、通知時間の設定のスクリーンショット](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [手順 5 - 呼び出しオーバーフロー >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[手順 5 通話 <br> オーバーフロー](#tab/call-overflow)

キューの最大数を超える呼び出しを処理する方法を選択します。

1. キュー内 **の最大呼び出しを設定します**。

2. 通話の最大数に達した場合に実行する操作を選択します。 通話を切断するか、リダイレクトできます。 次のいずれかの接続先に通話をリダイレクトすることをお勧めします。
    - **組織内のユーザー** - 音声通話を受信できる組織内のユーザー
    - **音声アプリ** - 自動応答または別の通話キュー。 (この宛先を選ぶときに、自動応答または通話キューに関連付けられているリソース アカウントを選ぶ。
    - **外部電話番号** - 任意の電話番号。 次の形式を使用します: +[国コード][郵便番号][電話番号]
    - **ボイス** メール - 作成したチームのボイス メールボックスを使用できます。

    ![呼び出しオーバーフロー設定のスクリーンショット](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [手順 6 - 通話のタイムアウト>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[手順 6 通話 <br> タイムアウト](#tab/call-timeout)

通話がキュー内で待ち時間が長すぎる場合に実行する処理を選択します。

1. 通話タイムアウト **を設定する: 最大待ち時間**。

2. 通話がタイムアウトした場合に実行する操作を選択します。通話を切断するか、リダイレクトできます。 次のいずれかの接続先に通話をリダイレクトすることをお勧めします。
    - **組織内のユーザー** - 音声通話を受信できる組織内のユーザー
    - **音声アプリ** - 自動応答または別の通話キュー。 (この宛先を選ぶときに、自動応答または通話キューに関連付けられているリソース アカウントを選ぶ。
    - **外部電話番号** - 任意の電話番号。 次の形式を使用します: +[国コード][郵便番号][電話番号]
    - **ボイス** メール - 作成したチームのボイス メールボックスを使用できます。

    ![通話タイムアウト設定のスクリーンショット](../media/call-queue-timeout-handling.png)

3. **[保存]** をクリックします。

これで通話キューのセットアップが完了します。 次に、自動応答 [を設定できます](create-a-phone-system-auto-attendant-smb.md)。

---

