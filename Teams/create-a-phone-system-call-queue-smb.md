---
title: Microsoft Teams で通話キューを作成する
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Microsoft Teams で通話キューを設定する方法について説明します。 通話キューは、あいさつメッセージ、保留音楽、通話リダイレクト、その他の機能を提供します。
ms.openlocfilehash: 2a1f16d9cde74988e082736f4d50f101fa0d6759
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486872"
---
# <a name="create-a-call-queue"></a>呼び出しキューを作成する

通話キューは、特定の問題や質問に対応できる組織内のユーザーに呼び出し元をルーティングします。 呼び出しは、 *エージェント* と呼ばれるキュー内のユーザーに一度に 1 つずつ配布されます。

呼び出しキューでは、次の情報が提供されます。

- あいさつメッセージ。
- ユーザーがキューで保留状態で待機している間の音楽。
- エージェントへの呼び出しルーティング ( *First In、First Out* (FIFO) 順)。
- キューオーバーフローとタイムアウトの処理オプション。

この記事の手順に従う前に、「 [Teams の自動応答と通話キューの計画](plan-auto-attendant-call-queue.md) 」を読み、 [作業の開始手順](plan-auto-attendant-call-queue.md#getting-started)に従っていることを確認してください。

## <a name="whats-new-for-call-queues-in-the-past-6-months"></a>過去 6 か月間の通話キューの新機能

- 8 月
  - **通話キューのメイン あいさつ文にあいさつメッセージ** (Text to Speech (TTS)) を追加できるようになりました。
  - **ボイスメールをスキップするシステム メッセージ** 制御は、共有ボイスメールにルーティングするときに公開されるようになりました。これは、 **あいさつメッセージ** プロンプトの追加にも適用されます。

## <a name="steps-to-create-a-call-queue"></a>呼び出しキューを作成する手順

呼び出しキューを設定する手順は次のとおりです。

1. 一般的な情報を設定する
1. あいさつ文と音楽を設定する
1. 通話応答を設定する
1. エージェントを選択して割り当てる
1. 呼び出しオーバーフロー処理を設定する
1. 呼び出しタイムアウト処理を設定する

記事で説明されている手順では、Teams 管理センターを使用して通話キューを作成します。 PowerShell を使用して呼び出しキューを作成する手順については、「 [PowerShell コマンドレットを使用した通話キューの作成](create-a-phone-system-call-queue-via-cmdlets.md)」を参照してください。

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>次の手順に従って通話キューを設定します

# <a name="step-1-general-info"></a>[手順 1: 一般的な情報](#tab/general-info)

## <a name="step-1-set-up-general-information"></a>手順 1: 一般的な情報を設定する

通話キューを設定するには、 [Teams 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2066851)で **[音声**] を展開し、[ **通話キュー**] を選択して、[ **追加**] を選択します。

上部のボックスに通話キューの名前を入力します。

### <a name="add-a-resource-account"></a>リソース アカウントを追加する

既存のリソース アカウントを追加するには:

1. [ **リソース アカウント**] の [ **追加** ] ボタンをクリックして、この呼び出しキューのリソース アカウントを追加します。
1. [ **アカウントの追加]** ウィンドウで、追加するリソース アカウントを検索します。
1. この呼び出しキューに割り当てるリソース アカウントの横にある [ **追加]** ボタンを選択します。
1. ウィンドウの下部にある [ **追加** ] ボタンを選択します。

リソース アカウントを作成する必要がある場合:

1. [ **リソース アカウント**] の [ **追加** ] ボタンをクリックして、この呼び出しキューのリソース アカウントを追加します。
1. [ **アカウントの追加]** ウィンドウで、結果ドロップダウンをプルする文字のセットを検索します。
1. 結果の下部にある **[+ リソース アカウントの追加** ] ボタンを選択します。
1. [リソース アカウントの追加] ウィンドウで、次の **操作を行います** 。
    1. わかりやすい **表示名** を入力します。これは、エージェントに表示されます。
    1. リソース アカウントのわかりやすい **ユーザー名** を入力します。
    1. **[リソース アカウントの種類**] ドロップダウンを選択し、[**通話キュー**] を選択します。
1. ウィンドウの下部にある [ **保存** ] ボタンを選択します。
1. [ **リソース アカウント** ] ウィンドウで、[ **追加** ] ボタンを選択します。

エージェントは、着信呼び出しを受け取ると、リソース アカウント名を表示します。

詳細については、「 [Teams リソース アカウントの管理](manage-resource-accounts.md)」を参照してください。

### <a name="assign-a-calling-id-optional"></a>呼び出し元 ID を割り当てる (省略可能)

**Teams チャネル/コラボレーション通話デスクトップ ユーザーと、標準通話キューを持つ Teams モバイル クライアント ユーザーで使用できます。**

エージェントの発信発信者番号を割り当てるには、電話番号で 1 つ以上のリソース アカウントを指定します。 エージェントは、発信呼び出しのたびに使用する発信発信者番号を選択できます。 通話アプリ内では、エージェントは通話キュー (CQ) /自動応答 (AA) 番号または独自の個人用の直接内向きダイヤル (DID) を使用できます。

> [!NOTE]
> 呼び出し ID の目的で使用されるリソース アカウントには **、Microsoft Teams 電話リソース アカウント** ライセンスが必要であり、次のいずれかが割り当てられている必要があります。
>
> - 通話プランのライセンスと電話番号が割り当てられている
> - オペレーター接続の電話番号が割り当てられている
> - オンライン音声ルーティング ポリシー (直接ルーティングを使用する場合は電話番号の割り当ては省略可能)

1. [ **呼び出し元 ID の割り当て**] で、[ **追加** ] ボタンを選択します。
1. [ **アカウントの追加]** ウィンドウで、エージェントが発信呼び出し元 ID の目的で使用できるようにするリソース アカウントを検索します。
1. 割り当てられた電話番号を持つリソース アカウントの横にある [ **追加]** ボタンを選択します。
1. ウィンドウの下部にある [ **追加]** ボタンを選択します。

割り当てられた電話番号を持つリソース アカウントがない場合:

1. [ **リソース アカウント**] の [ **追加** ] ボタンをクリックして、リソース アカウントを追加します。
1. [ **アカウントの追加]** ウィンドウで、結果ドロップダウンをプルする文字のセットを検索します。
1. 結果の下部にある **[+ リソース アカウントの追加** ] ボタンを選択します。
1. [リソース アカウントの追加] ウィンドウで、次の **操作を行います** 。
    1. 受信者を呼び出すために表示されるわかりやすい **表示名** を入力します。
    1. リソース アカウントのわかりやすい **ユーザー名** を入力します。
    1. **[リソース アカウントの種類**] ドロップダウンを選択し、[**通話キュー**] を選択します。
1. ウィンドウの下部にある [ **保存** ] ボタンを選択します。
1. [ **リソース アカウント** ] ウィンドウで、[ **追加** ] ボタンを選択します。

この新しいリソース アカウントを作成して ID を呼び出した後も、次のことを行う必要があります。

- [Teams Phone リソース アカウント ライセンス](manage-resource-accounts.md#assign-a-license)を割り当てる
- Microsoft 通話プランのライセンスの割り当て、オペレーター接続の電話番号の割り当て、またはダイレクト ルーティングのオンライン音声ルーティング ポリシーの割り当て
- Microsoft 通話プランを使用している場合は、 [サービスの電話番号をリソース アカウント](manage-resource-accounts.md#assign-a-service-number)に割り当てます

### <a name="set-the-call-queue-language"></a>呼び出しキューの言語を設定する

[サポートされている言語](create-a-phone-system-call-queue-languages.md)を選択します。

この言語は、システムによって生成された音声プロンプトとボイスメールの文字起こしに使用されます (有効にした場合)。

言語を選択したら、[**通話キューの追加**] ページの下部にある [**次へ**] ボタンを選択します。

# <a name="step-2-greeting-and-music"></a>[手順 2: あいさつと音楽](#tab/greeting-music)

## <a name="step-2-add-a-greeting-and-on-hold-music"></a>手順 2: あいさつ文と保留音を追加する

*新規 - 通話キューのメイン **あいさつ文にあいさつメッセージ** (Text to Speech (TTS)) を追加できるようになりました。*

呼び出し元がキューに到着したときに、呼び出し元への *あいさつ* を再生するかどうかを指定します。

- **[オーディオ ファイルの再生**] を選択した場合は、再生するあいさつ文を含む MP3、WAV、または WMA ファイルをアップロードする必要があります。 アップロードされた記録は、5 MB を超えてはなりません。

- **[あいさつメッセージの入力**] を選択すると、通話キューが通話に応答したときに入力したテキスト (最大 1,000 文字) が読み取られます。

Teams は、キューに保留されている間、発信者に既定 *の音楽を提供します*。

- Teams 通話キューで提供される既定の音楽には、組織が支払う使用料は無料です。
- 特定のオーディオ ファイルを再生する場合は、[ **オーディオ ファイルの再生** ] を選択し、MP3、WAV、または WMA ファイルをアップロードします。

> [!NOTE]
> お客様は、Microsoft Teams サービスで音楽またはオーディオ ファイルを使用するために必要なすべての権利とアクセス許可を個別にクリアし、セキュリティで保護する責任があります。これには、関連するすべての権利保有者 (アーティストを含む) からオーディオ ファイル内の音楽、サウンド エフェクト、オーディオ、ブランド、名前、およびその他のコンテンツに含まれる知的財産やその他の権利が含まれる場合があります。 アクター、パフォーマー、音楽家、音楽ライター、作曲家、レコード ラベル、音楽パブリッシャー、ユニオン、ギルド、権利団体、集合管理組織、音楽著作権、サウンド エフェクト、オーディオ、その他の知的財産権を所有、管理、ライセンスするその他の当事者。

あいさつ文と保留音を選択したら、[**通話キューの追加**] ページの下部にある [**次へ**] ボタンを選択します。

# <a name="step-3-call-answering"></a>[手順 3: 通話応答](#tab/call-answering)

## <a name="step-3-set-up-who-will-answer-incoming-calls"></a>手順 3: 着信に応答するユーザーを設定する

エージェントを [呼び出しキューに追加するための前提条件を確認します](plan-auto-attendant-call-queue.md#prerequisites)。

### <a name="teams-channel"></a>Teams チャネル

Teams チャネルを介して最大 200 のエージェントを追加できます。 キューにチャネルを追加するには、チームのメンバーであるか、チャネルの作成者または所有者である必要があります。

[Teams チャネルを使用してキューを管理する](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)場合:

1. [ **チームの選択** ] ラジオ ボタンを選択し、[ **チャネルの追加]** を選択します。
1. 使用するチームを検索して選択し、[ **追加**] を選択します。
1. 使用するチャネル (標準チャネルのみがサポートされています) を選択し、[適用] を選択 **します**。

通話キューに Teams チャネルを使用する場合は、次のクライアントがサポートされます。

- Microsoft Teams Windows クライアント
- Microsoft Teams Mac クライアント

> [!NOTE]
> このオプションを使用すると、呼び出しキューが完全に動作するまでに最大で 24 時間かかる場合があります。
>
> チームに 200 人を超えるメンバーがいる場合は、最初の 200 人のメンバーのみが、通話キューにエージェントとしてアルファベット順に追加されます。

### <a name="users-and-groups"></a>ユーザーとグループ

グループを介して、最大 20 個のエージェントを個別に追加し、最大 200 個のエージェントを追加できます。

個々のユーザーまたはグループをキューに追加する場合は、次のようにします。

1. [ **ユーザーとグループの選択]** ラジオ ボタンを選択します。

**キューにユーザーを追加** するには:

1. [ **ユーザーの追加]** を選択し、ユーザーを検索して [ **追加]** をクリックし、[ **追加**] をクリックします。

**グループを** キューに追加するには:

1. [ **グループの追加]** を選択し、グループを検索して [ **追加]** をクリックし、[ **追加**] をクリックします。 
    1. 配布リスト、セキュリティ グループ、Microsoft 365 グループ、または Microsoft Teams チームを使用できます。

> [!NOTE]
> グループに追加された新しいユーザーは、最初の呼び出しが到着するまでに最大 8 時間かかる場合があります。
>
> グループに 200 を超えるメンバーがある場合は、最初の 200 人のメンバーのみがアルファベット順でエージェントとして呼び出しキューに追加されます。

### <a name="conference-mode"></a>会議モード

**電話会議モード** では、エージェントが呼び出しを受け入れた後に発信者がエージェントに接続するまでにかかる時間が短縮されます。 会議モードを機能させるには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。

- Microsoft Teams デスクトップ クライアント、Android アプリ、または iOS アプリの最新バージョン
- Microsoft Teams 電話 バージョン 1449/1.0.94.2020051601 以降
  
エージェントの Teams アカウントは TeamsOnly モードに設定する必要があります。 要件を満たしていないエージェントは、通話ルーティングリストに含まれません。 エージェントが互換性のあるクライアントを使用している場合は、通話キューの電話会議モードを有効にすることをお勧めします。

> [!NOTE]
> 場所ベースのルーティングが有効になっているダイレクト ルーティング ゲートウェイから通話がキューにルーティングされている場合、会議モードはサポートされません。
>
> 電話会議モードは、通話がSkype for Business Serverからキューにルーティングされる場合はサポートされません。
> 
> Teams ユーザーが通話キューを使用して通話を参照/転送する必要がある場合は、会議モードが必要です。
>
> エージェントは、最初に通話に参加するときに、キュー内で構成された保留音を最大 2 秒間聞き取ることがあります。


> [!TIP]
> **会議モード** を **[オン]** に設定することをお勧めします。

通話応答オプションを選択したら、[通話 **キューの追加**] ページの下部にある [**次へ**] ボタンを選択します。

# <a name="step-4-agent-routing"></a>[手順 4: エージェント のルーティング](#tab/agent-routing)

## <a name="step-4-select-your-agent-routing-options"></a>手順 4: エージェント ルーティング オプションを選択する

**ルーティングメソッド** は、エージェントがキューから呼び出しを受信する順序を決定します。

次のオプションから選択します。

- **アテンダント ルーティング** では、キュー内のすべてのエージェントが同時にリングされます。 呼び出しを受け取る最初の呼び出しエージェントが呼び出しを取得します。

- **シリアル ルーティング** では、通話エージェントの一覧で指定された順序ですべての **呼び出しエージェント** が 1 つずつリングされます。 エージェントが通話を閉じるか、または呼び出しを受け取らない場合、呼び出しは次のエージェントを呼び出します。 これは、呼び出しが取り上げられるかタイムアウトするまで繰り返されます。

- **ラウンド ロビンは** 、各呼び出しエージェントがキューから同じ数の呼び出しを取得するように、着信呼び出しのルーティングのバランスを取ります。 このルーティング方法は、受信販売環境で、すべての通話エージェント間で機会が均等になるようにすることが望ましい場合があります。

- **最長アイドル時間は、最も長い** 時間アイドル状態になっているエージェントに各呼び出しをルーティングします。 エージェントのプレゼンス状態が使用可能な場合、エージェントはアイドル状態と見なされます。 プレゼンス状態が [使用可能] でないエージェントは、プレゼンスを [利用可能] に変更するまで通話を受信できません。

**ルーティング方法** を **ラウンド ロビン** または **最長アイドル** 状態に設定することをお勧めします。

> [!NOTE]
> エージェントで [コンプライアンス記録](teams-recording-policy.md) が有効になっている場合、 **会議モード** と **アテンダント ルーティング** の組み合わせはサポートされていません。 **会議モード** を使用する必要がある場合は、ルーティング **方法** として **シリアル ルーティング**、**ラウンド ロビン**、または **最長アイドル** 状態を選択します。 **アテンダント ルーティング** を使用する必要がある場合は、**会議モード** を **[オフ]** に設定します。
>
> **最長アイドル状態** を使用していて、使用可能なエージェントよりもキュー内の呼び出しが少ない場合は、最初の 2 つの最長アイドル エージェントのみがキューからの呼び出しで表示されます。
>
> **最長アイドル状態** を使用している場合、エージェントが使用できなくなった直後にキューからの呼び出しを受信したり、使用可能になった後にキューからの呼び出しを受信する時間が短い場合があります。
>
> エージェントへの通話キュー呼び出しプレゼンテーションは、場所ベースのルーティングの制限と競合する可能性があります。 この場合、エージェントは通話トーストを受け取りますが、通話に応答することはできません。 この状態は、別のエージェントが呼び出しに応答できるようになるか、呼び出し元がハングアップするか、通話キューのタイムアウト状態が発生するまで続行されます。  

### <a name="presence-based-call-routing"></a>プレゼンス ベースの呼び出しルーティング

**プレゼンス ベースの呼び出しルーティング** では、呼び出しエージェントの可用性状態を使用して、選択したルーティング方法の呼び出しルーティング リストにエージェントを含める必要があるかどうかを判断します。

可用性の状態が **[使用可能]** に設定されている通話エージェントは、通話ルーティングリストに含まれ、通話を受信できます。 可用性の状態が他の状態に設定されているエージェントは、呼び出しルーティング リストから除外され、可用性の状態が **[使用可能**] に戻るまで呼び出しを受け取りません。

任意 **のルーティング方法を使用して、プレゼンス ベースの呼び出し** ルーティングを有効にすることができます。

エージェントが呼び出しの取得をオプトアウトした場合、可用性の状態が設定されているかどうかに関係なく、エージェントは呼び出しルーティング リストに含まれません。

**プレゼンス ベースのルーティング** を有効にすることをお勧めします。

> [!NOTE]
> ルーティング方法として **[最長アイドル時間** ] が選択されている場合、プレゼンス ベースのルーティングトグルが **オフ** で淡色表示になっている場合でも、プレゼンスベースのルーティングが必要であり、自動的に有効になります。
>
> プレゼンス ベースのルーティングが有効になっていて、キューに複数の呼び出しがある場合、システムは、プレゼンス状態に関係なく、これらの呼び出しをエージェントに同時に表示します。 このアクションは、特に一部のエージェントがエージェントに提示された最初の呼び出しに応答しない場合に、エージェントに対して複数の呼び出し通知が発生します。
>
> **プレゼンス ベースのルーティング** を使用する場合、エージェントが使用できなくなった直後にキューからの呼び出しを受信したり、使用可能になった後にキューからの呼び出しを受信する時間が短い場合があります。
>
> プレゼンス ベースのルーティングが有効になっている場合、Skype for Business クライアントを使用するエージェントは呼び出しルーティングリストに含まれません。 Skype for Businessを使用するエージェントがある場合は、プレゼンス ベースの呼び出しルーティングを有効にしないでください。

### <a name="call-agents-can-opt-out-of-taking-calls"></a>通話エージェントは、通話の受け取りをオプトアウトできます

呼び出しエージェントが通話をオプトアウトできるかどうかを指定できます。

通話エージェントを有効にすると **、通話の受け取りをオプトアウトできます**。

### <a name="agent-alert-time"></a>エージェントのアラート時間

**エージェントアラート時間** は、キューが次のエージェントに呼び出しをリダイレクトするまでにエージェントの電話が鳴る時間を指定します。

**エージェントのアラート時間** を **20 秒** に設定することをお勧めします。

エージェント通話ルーティング オプションを選択したら、[**通話キューの追加**] ページの下部にある [**次へ**] ボタンを選択します。

# <a name="step-5-call-overflow"></a>[手順 5: オーバーフローを呼び出す](#tab/call-overflow)

## <a name="step-5-set-how-to-handle-call-overflow"></a>手順 5: 呼び出しオーバーフローを処理する方法を設定する

**キュー内の最大呼び出し** 数は、任意の時点でキュー内で待機できる呼び出しの最大数を指定します。

既定値は 50 ですが、範囲は 0 ~ 200 です。

この制限に達すると、[呼び出しの最大数に達したとき] 設定で指定されたとおり **に呼び出しが** 処理されます。

呼び出しを **切断** するか、呼び出しルーティング先のいずれかに **リダイレクト** するかを選択できます。

たとえば、呼び出し元がキュー内のエージェントのボイスメールを残す場合があります。

*新規 - **ボイスメール システム メッセージ制御をスキップ** すると、共有ボイスメールへのルーティング時に公開されるようになりました。これは、 **あいさつメッセージ** プロンプトの追加にも適用されます。*

外部転送については、「前提条件と[外部電話番号の転送 -](create-a-phone-system-auto-attendant.md?tabs=additional-resources) 番号の書式設定に関する技術的な詳細」を参照[してください](./plan-auto-attendant-call-queue.md#prerequisites)。

> [!NOTE]
> 呼び出しの最大数が 0 に設定されている場合、あいさつメッセージは再生されません。

通話オーバーフロー処理オプションを選択したら、[通話 **キューの追加**] ページの下部にある [**次へ**] ボタンを選択します。

# <a name="step-6-call-timeout"></a>[手順 6: 呼び出しタイムアウト](#tab/call-timeout)

## <a name="step-6-set-how-to-handle-call-timeouts"></a>手順 6: 呼び出しタイムアウトを処理する方法を設定する

**呼び出しタイムアウト: 最大待機時間** は、呼び出しがリダイレクトまたは切断されるまでのキュー内で保留できる最大時間を指定します。

0 秒から 45 分の値を指定できます。

呼び出しを **切断** するか、呼び出しルーティング先のいずれかに **リダイレクト** するかを選択できます。

たとえば、呼び出し元がキュー内のエージェントのボイスメールを残す場合があります。

*新規 - **ボイスメール システム メッセージ制御をスキップ** すると、共有ボイスメールへのルーティング時に公開されるようになりました。これは、 **あいさつメッセージ** プロンプトの追加にも適用されます。*

外部転送については、「前提条件と[外部電話番号の転送 -](create-a-phone-system-auto-attendant.md?tabs=additional-resources) 番号の書式設定に関する技術的な詳細」を参照[してください](./plan-auto-attendant-call-queue.md#prerequisites)。

通話タイムアウト処理オプションを選択したら、[通話 **キューの追加**] ページの下部にある [**送信]** ボタンを選択します。

---

## <a name="resources-for-complex-scenarios"></a>複雑なシナリオのリソース

### <a name="summary-of-recommended-call-queue-settings"></a>推奨される通話キュー設定の概要

次の設定をお勧めします。

- **会議モード** を **オンにする**
- **ラウンド ロビン** または **最長アイドル** 状態への **ルーティング方法**
- **プレゼンス ベースのルーティング** から **On** へのルーティング
- **エージェントのアラート時間:** **20 秒** まで

### <a name="call-queue-feature-compatibility"></a>通話キュー機能の互換性

|機能                          |Teams Desktop<sup>1</sup> |Teams Web | Teams Mobile<sup>2</sup> |Lync |IP 電話 | 標準呼び出しキュー |チャネル ベースの呼び出しキュー | コメント |
|:--------------------------------|:------------------------:|:--------:|:--------------:|:---:|:--------:|:--------------------:|:------------------------:|:--------|
|**エージェント ルーティング方法**        |                          |          |                |     |          |                      |                          |   |
|`Attendant Routing`              |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |*既定値*     |
|`Longest Idle`<sup>3</sup>       |Y                         |Y         |Y               |N    |Y         |Y                     |Y                         |*推奨* |
|`Round Robin`                    |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |*推奨* |
|`Serial`                         |Y                         |Y         |Y               |Y    |Y         |Y<sup>4</sup>         |Y<sup>4</sup>             |   |
|**エージェント ルーティング オプション**        |                          |          |                |     |          |                      |                          |   |
|`Presence Based Routing`<sup>3</sup>|Y                      |Y         |Y               |N    |Y         |Y                     |Y                         |*既定値* |
|`Agents can Opt-out`               |Y                       |Y         |Y               |Y<sup>7</sup>|Y<sup>7</sup>|Y          |Y                         |*既定値*     |
|**転送モード**               |                          |          |                |     |          |                      |                          |   |
|`Conference Mode`<sup>5</sup>    |Y                         |Y         |Y               |N    |Y<sup>6</sup>|Y                  |Y                         |*既定値* |
|`Transfer Mode`                  |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |   |
|**共同通話**        |                          |          |                |     |          |                      |                          |   |
|`Channel Based Queues`             |Y                       |N         |N               |N    |N         |N/a                   |Y<sup>8</sup>             |   |
|**動的呼び出し元 ID**            |                          |          |                |     |          |                      |                          |   |
|`Standard call queue`            |Y                         |Y         |Y               |N    |N         |Y                     |N/a                       |   |
|`Channel based call queue`       |Y                         |N/a       |N/a             |N/a  |N/a       |N/a                   |Y                         |   |
|**PSTN 接続方法**    |                          |          |                |     |          |                      |                          |注 9 を参照してください   |
|`Calling Plans`                  |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |   |
|`Direct Routing`                 |Y                         |Y         |Y               |N    |N         |Y                     |Y                         |   |
|`Operator Connect`               |Y                         |Y         |Y               |     |          |Y                     |Y                         |   |
|**他**                |                          |          |                |     |          |                      |                          |   |
|`Call toast shows Resource Account Name` |Y                 |N         |Y               |Y    |          |Y                     |Y                         |              |

#### <a name="notes"></a>メモ

1. Microsoft Teams Windows クライアント、Microsoft Teams Mac クライアント、仮想化デスクトップ インフラストラクチャ上の Microsoft Teams。
2. Microsoft Teams iPhone アプリ、Microsoft Teams Android アプリ。
3. エージェント ルーティング方法で [最長アイドル時間] を選択すると、プレゼンス ベースのルーティングが自動的に有効になります。
4. 個々のユーザーを標準呼び出しキューの一部として追加する場合にのみ、順序を設定できます。 配布リストまたは Teams チャネルが使用されている場合、順序はアルファベット順になります。
5. 場所ベースのルーティングが有効になっているダイレクト ルーティング ゲートウェイから通話がキューにルーティングされている場合、会議モードはサポートされません。
6. Microsoft Teams 電話のみ。
7. [ユーザー設定ポータル] ページの [ [https://aka.ms/vmsettings](https://aka.ms/vmsettings).
8. パブリック チャネルのみがサポートされます。
9. 自動応答と通話キューでは、PSTN 接続方法間で通話を転送できません。

### <a name="supported-clients"></a>サポートされるクライアント

呼び出しキュー内の呼び出しエージェントでは、次のクライアントがサポートされています。

- Skype for Business デスクトップ クライアント 2016 (32 ビットバージョンと 64 ビット バージョン)
- Lync デスクトップ クライアント 2013 (32 ビットおよび 64 ビット バージョン)
- Microsoft Teams でサポートされているすべての IP 電話モデル。 [「Skype for Business Online の電話を取得する](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)」を参照してください。
- Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)
- Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)
- iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)
- Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)
- Microsoft Teams Windows クライアント (32 ビットおよび 64 ビット バージョン)
- Microsoft Teams Mac クライアント
- [仮想化デスクトップ インフラストラクチャ](teams-for-vdi.md)上の Microsoft Teams (Windows Virtual Desktop、Citrix、VMware)
- Microsoft Teams iPhone アプリ
- Microsoft Teams Android アプリ

  > [!NOTE]
  > ダイレクト ルーティング番号が割り当てられた通話キューでは、クライアント、Lync クライアント、またはエージェントとしての ip Phone Skype for Business Skype for Businessサポートされません。 Teams クライアントは、 [Teams のみの共存モード](setting-your-coexistence-and-upgrade-settings.md)でのみサポートされます。

### <a name="call-queue-diagnostic-tool"></a>キュー診断ツールの呼び出し

管理者の場合は、次の診断ツールを使用して、通話キューが通話を受信できることを検証できます。

1. 以下の **[テストの実行]** を選択すると、診断が Microsoft 365 管理センターに表示されます。

   > [!div class="nextstepaction"]
   > [テストの実行: Teams 通話キュー](https://aka.ms/TeamsCallQueueDiag)

2. [実行] 診断ウィンドウで、[**ユーザー名] または [Email**] フィールドにリソース アカウントを入力し、[**テストの実行**] を選択します。

3. テストでは、テナント、ポリシー、リソース アカウントの構成に対処するための最適な次の手順が返され、呼び出しキューが呼び出しを受信できることを検証します。

### <a name="related-topics"></a>関連項目

[Microsoft Teams 電話で得られる内容を次に示します。](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)