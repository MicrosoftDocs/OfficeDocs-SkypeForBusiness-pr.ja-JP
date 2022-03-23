---
title: 次のページで呼び出しキューをMicrosoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Microsoft Teams で大規模な組織の通話キューを設定する方法について説明します。この機能は、あいさつメッセージ、保留音楽、通話リダイレクト、その他の機能を提供します。
ms.openlocfilehash: 6b6f143a4fefc90ffabf282814147796d4b3baf3
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711911"
---
# <a name="create-a-call-queue"></a>呼び出しキューを作成する

通話キューは、特定の問題や質問に役立つ組織内のユーザーに発信者をルーティングする方法を提供します。 呼び出しは、キュー内のユーザー (エージェントと呼ばれる) に一度に 1 回配布 *されます*。 

> [!TIP]
> この記事は、大規模な組織向けです。 組織が小規模企業の場合は、「通話キューの作成 - 代わりに小規模ビジネス向け [チュートリアル」を](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) 参照してください。

呼び出しキューには、次の機能があります。

- あいさつメッセージ。

- ユーザーがキューで保留を待機している間の音楽。

- コール ルーティング - *First In,First Out* (FIFO) order - to agents.

- キューのオーバーフローとタイムアウトの処理オプション。

この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md) 自動応答と通話キューの計画」を読[](plan-auto-attendant-call-queue.md#getting-started)み、概要の手順に従ってください。

**詳細については [、以下の「Call Queue Feature Compatibility matrix](#call-queue-feature-compatibility) (呼び出しキュー機能の互換性マトリックス)」を参照してください。**

## <a name="video-demonstration"></a>ビデオデモ

このビデオでは、通話キューを作成する方法の基本的な例をTeams。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a>呼び出しキューを作成する

通話キューを設定するには、Teams センターで 、[音声] を展開し、[通話キュー] をクリックして、[追加] をクリック **します**。

通話キューの名前を入力します。

## <a name="resource-accounts"></a>リソース アカウント

![リソース アカウント設定のスクリーンショット。](media/call-queue-name-language.png)

[**アカウントの追加]** をクリックし、この呼び出しキューで使用するリソース アカウントを検索し、[追加] をクリックして、[追加] をクリック **します**。 (エージェントは、着信呼び出しを受信すると、リソース アカウント名を表示します)。

詳細については、「リソース アカウントの[管理」Teams参照してください](manage-resource-accounts.md)。

## <a name="dynamic-caller-id"></a>動的呼び出し元 ID

![呼び出し元 ID 設定のスクリーンショット。](media/call-queue-assign-calling-id.png)

**チャネル/コラボレーションTeamsデスクトップ ユーザー、および標準の通話キューを使用Teamsクライアント ユーザーが使用できます。**

電話番号で 1 つ以上のリソース アカウントを指定することで、エージェントの発信呼び出し元 ID 番号を割り当てできます。 エージェントは、発信呼び出しごとに使用する発信呼び出し元 ID 番号を選択できます。

[**追加**] をクリックし、エージェントが発信呼び出しを行う際に発信者番号の目的で使用するリソース アカウントを検索し、[追加] をクリックして、[追加] をクリック **します**。

**標準呼び出しキュー**

デスクトップ Teams標準の通話キューでは、通話キューのメンバーの呼び出し元 ID を、通話キューのサービス番号または適切な自動応答に直接設定します。 詳細については、「Manage [caller ID policies in Microsoft Teams」を参照してください](caller-id-policies.md)。

> [!NOTE]
> ID を呼び出す目的で使用されるリソース アカウントには、仮想Microsoft Teams 電話システムライセンスが割り当てられている必要があります。
>
> - 通話プランのライセンスと割り当てられた電話番号
> - オペレーターがConnect電話番号を割り当てる
> - オンライン音声ルーティング ポリシー (直接ルーティングを使用する場合、電話番号の割り当ては省略可能)


## <a name="language"></a>言語

![言語設定のスクリーンショット。](media/call-queue-language.png)

サポートされている [言語を選択します](create-a-phone-system-call-queue-languages.md)。 この言語は、システムで生成された音声プロンプトとボイスメールのトランスクリプション (有効にした場合) に使用されます。

## <a name="greetings-and-music-on-hold-in-queue"></a>キュー内のあいさつや保留音

![キュー設定でのあいさつメッセージと保留音のスクリーンショット。](media/call-queue-greetings-music.png)

発信者がキューに到着するときに、発信者にあいさつメッセージを再生する場合に指定します。 再生するあいさつメッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。 アップロードされた記録は 5 MB 以下にできます。

Teamsキューで保留されている間、呼び出し元に既定の音楽を提供します。 通話キューで提供される既定Teams、組織が支払う使用料金は無料です。 特定のオーディオ ファイルを再生する場合は、[オーディオ  ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。

> [!NOTE]
> お客様は、Microsoft Teams サービスで音楽またはオーディオ ファイルを使用するために必要なすべての権利とアクセス許可を個別にクリアし、保護する責任を負います。このサービスには、音楽、サウンド エフェクト、オーディオ、ブランド、名前、オーディオ ファイル内のその他のコンテンツに含まれる知的財産、その他の権利が含まれます。このコンテンツには、アーティスト、アクター、アーティスト、アクターが含まれる場合があります。 パフォーマー、音楽家、曲者、音楽家、レコード ラベル、音楽パブリッシャー、ユニオン、ギルド、権利団体、集合管理組織、音楽著作権、サウンド エフェクト、オーディオ、その他の知的財産権を所有、制御、またはライセンスを取得するその他の当事者。

## <a name="call-agents"></a>エージェントの呼び出し

エージェントを [呼び出しキューに追加するための前提条件を確認します](plan-auto-attendant-call-queue.md#prerequisites)。

![通話キューのユーザーとグループの設定のスクリーンショット。](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Teams チャネル

1 つのチャネルを介して最大 200 のエージェントTeamsできます。 チャネルをキューに追加するには、チームのメンバー、作成者、またはチャネルの所有者である必要があります。

キューの管理に [Teamsを](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)使用する場合は、[チームの選択] オプションを選択し、[チャネルの追加 **] をクリックします**。 使用するチームを検索して選択し、[追加] をクリック **します**。 使用するチャネルを選択し (標準チャネルのみサポートされています)、[適用] をクリック **します**。 

次のクライアントは、呼び出しキューに対して Teams チャネルを使用する場合にサポートされます。 

  - Microsoft Teams Windows クライアント
  - Microsoft Teams Mac クライアント

> [!NOTE]
> このオプションを使用する場合、通話キューが完全に動作するには最大 24 時間かかる場合があります。

##### <a name="users-and-groups"></a>ユーザーとグループ

最大 20 個のエージェントを個別に追加できます。また、グループ経由で最大 200 個のエージェントを追加できます。

キューに個々のユーザーまたはグループを追加する場合は、[ユーザーとグループの選択 **] オプションを選択** します。 

キューにユーザーを追加するには、[ユーザーの追加] をクリックし、ユーザーを検索し、[追加] をクリックして、[追加] をクリック **します**。

キューにグループを追加するには、[グループの追加] をクリックし、グループを検索し、[追加] **をクリックして**、[追加] をクリック **します**。 配布リスト、セキュリティ グループ、およびグループまたはチームMicrosoft 365使用Microsoft Teamsできます。

> [!NOTE]
> グループに追加された新しいユーザーは、最初の呼び出しが到着するために最大 8 時間かかる場合があります。

## <a name="call-routing"></a>通話ルーティング

![電話会議モードとルーティング方法の設定のスクリーンショット。](media/call-queue-conference-mode-routing-method.png)

**電話会議モード** では、エージェントが呼び出しを受け入れてから、呼び出し元がエージェントに接続するのにかかる時間が大幅に短縮されます。 電話会議モードを機能するには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。

  - デスクトップ クライアント、Android Microsoft Teams iOS アプリの最新バージョン
  - Microsoft Teams 電話 バージョン 1449/1.0.94.2020051601 以降
  
エージェントのTeamsアカウントは、Teamsモードに設定する必要があります。 要件を満たしていないエージェントは、通話ルーティングの一覧には含まれません。 エージェントが互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。

> [!NOTE]
> 電話呼び出しが、場所ベースのルーティングが有効になっているダイレクト ルーティング ゲートウェイからキューにルーティングされる場合、電話会議モードはサポートされません。

> [!TIP]
> 会議 **モードを [オン** ] **に** 設定する方法をお勧めします。

**ルーティング方法は** 、エージェントがキューから呼び出しを受信する順序を決定します。 次のオプションから選択します。

- **アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。 呼び出しを受け取る最初の呼び出しエージェントが呼び出しを取得します。

- **シリアル ルーティングでは** 、すべての呼び出しエージェントが[通話エージェント] の一覧で指定された順序 **で 1 つ 1 つリング** されます。 エージェントが通話を閉じ、または呼び出しを受け取らない場合、呼び出しは次のエージェントを呼び出します。 この操作は、呼び出しが取り込まれるか、または時間が切れるまで繰り返されます。

- **ラウンド ロビンは** 、着信呼び出しのルーティングのバランスを取り、各呼び出しエージェントがキューから同じ数の呼び出しを取得します。 このルーティング方法は、すべての通話エージェント間で均等な機会を確保するために、受信販売環境で望ましい場合があります。

- **アイドル時間が** 最も長いエージェントに各呼び出しをルーティングします。 エージェントのプレゼンス状態が [使用可能] の場合、エージェントはアイドル状態と見なされます。 プレゼンス状態が [利用できない] のエージェントは、プレゼンスを [利用可能] に変更するまで、通話を受信する資格を得られません。 

> [!TIP]
> [**ルーティング方法] を [****ラウンド ロビン] または [****最長アイドル]** に設定する方法をお勧めします。

> [!NOTE]
> エージェント [でコンプライアンス記録](teams-recording-policy.md) が有効になっている場合、 **会議モードと** アテンダント ルーティングの組み **合わせは** サポートされません。 会議モードを使用する必要 **がある場合は、[** ルーティング方法] として [ **シリアル** ルーティング]、[ **ラウンド** ロビン]、または [最長 **アイドル** ] **を選択します**。 アテンダント ルーティングを使用 **する必要がある場合は、[** 会議モード] **を [オフ]** に **設定します**。
> 
> 最長アイドル **状態を使用** し、キュー内の呼び出しが使用可能なエージェントよりも少ない場合、キューからの呼び出しでは、最初の 2 つの最も長いアイドル状態のエージェントだけが表示されます。
> 
> 最長アイドル **状態** を使用すると、エージェントが使用できなくなった直後にキューから呼び出しを受信する場合や、使用可能になった後にキューからの呼び出しを受信する時間が短い場合があります。
> 
> エージェントへの通話キュー呼び出しのプレゼンテーションは、場所ベースのルーティング制限と競合する可能性があります。 この場合、エージェントは呼び出しトーストを受け取りますが、呼び出しに応答する機能はありません。 この条件は、別のエージェントが呼び出しに応答できるまで、呼び出し元がハングアップするか、呼び出しキューのタイムアウト条件が発生するまで続行されます。  


![ルーティング、オプトアウト、およびアラート時間の設定のスクリーンショット。](media/call-queue-presence-agents-time.png)

**プレゼンス ベースのルーティングでは** 、呼び出しエージェントの可用性状態を使用して、選択したルーティング方法の呼び出しルーティング リストにエージェントを含める必要があるかどうかを判断します。 可用性の状態が [使用可能] に設定されている通話エージェント **は、通話** ルーティング リストに含まれており、通話を受信できます。 可用性の状態が他の状態に設定されているエージェントは、通話ルーティング リストから除外され、可用性の状態が [利用可能] に戻るまで通話を受信 **しません**。 

プレゼンス ベースの呼び出しルーティングは、どのルーティング方法でも有効にできます。

エージェントが呼び出しを受け取らない場合、エージェントは、可用性の状態が設定されているに関係なく、通話ルーティング リストに含まれません。 

> [!NOTE]
> ルーティング **方法として [最長** アイドル時間] が選択されている場合、プレゼンス ベースのルーティングのトグルが [オフ] および [グレー] になっている場合でも、プレゼンス ベースのルーティングが必要であり、自動的に有効になります。
>
> プレゼンス ベースのルーティングが有効ではなく、キュー内に複数の呼び出しがある場合、システムは、プレゼンス状態に関係なく、これらの呼び出しをエージェントに同時に表示します。 これにより、エージェントに対する複数の呼び出し通知が発生します。特に、一部のエージェントがエージェントに提示された最初の呼び出しに応答しない場合。
> 
> プレゼンス ベースのルーティングが有効Skype for Business、クライアントを使用するエージェントは、呼び出しルーティング リストに含まれません。 このサービスを使用するエージェントSkype for Business、プレゼンス ベースの呼び出しルーティングを有効にすることはできません。

> [!TIP]
> [ **プレゼンス ベースのルーティング] を** **[オン** ] に設定する方法をお勧めします。

**エージェント アラート時間は** 、キューが呼び出しを次のエージェントにリダイレクトする前に、エージェントの電話が鳴る時間を指定します。

> [!TIP]
> エージェント **のアラート時間を** **20 秒** に設定する方法をお勧めします。

## <a name="call-overflow-handling"></a>呼び出しオーバーフロー処理

![呼び出しオーバーフロー設定のスクリーンショット。](media/call-queue-overflow-handling.png)

**キュー内の最大呼び** 出し数は、特定の時点でキュー内で待機できる呼び出しの最大数を指定します。 既定値は 50 ですが、0 ~ 200 の範囲で指定できます。 この制限に達すると、呼び出しは [呼び出しの最大数に達した場合] 設定で指定された **方法で処理** されます。

通話を切断するか、任意の通話ルーティング先にリダイレクトすることができます。 たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。 外部転送については、「前提条件」と [「](plan-auto-attendant-call-queue.md#prerequisites) 外部電話番号の転送 - 番号の書式設定 [に関する技術的](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) な詳細」を参照してください。

> [!NOTE]
> 呼び出しの最大数が 0 に設定されている場合、あいさつメッセージは再生されません。

## <a name="call-timeout-handling"></a>呼び出しタイムアウト処理

![通話タイムアウト設定のスクリーンショット。](media/call-queue-timeout-handling.png)

**呼び出** しタイムアウト: 最大待機時間は、呼び出しがリダイレクトまたは切断される前にキューで保留にできる最大時間を指定します。 0 秒から 45 分の値を指定できます。

通話を切断するか、または通話ルーティング先の 1 つにリダイレクトすることができます。 たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。 外部転送については、「前提条件」と「 [外部電話番号の](plan-auto-attendant-call-queue.md#prerequisites) 転送 - 番号の書式設定 [に関する技術的](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) な詳細」を参照してください。

通話タイムアウト オプションを選択した後、[保存] を **クリックします**。

## <a name="summary-of-recommended-call-queue-settings"></a>推奨される通話キュー設定の概要

次の設定をお勧めします。

- **会議モードを** **[オン] に切り替えます。**
- **ラウンド ロビンまたは****最長アイドルへの****ルーティング方法**
- **プレゼンス ベースのルーティングを** **[オン] に設定する**
- **エージェントのアラート時間:** **~ 20 秒**


## <a name="call-queue-feature-compatibility"></a>通話キュー機能の互換性

|機能                          |Teams <sup>Desktop1</sup> |Teams <sup>Mobile2</sup> |Lync |IP 電話 | 標準呼び出しキュー |チャネル ベースの通話キュー | コメント |
|:--------------------------------|:------------------------:|:-----------------------:|:---:|:--------:|:--------------------:|:------------------------:|:-------------|
|**エージェントのルーティング方法**        |                          |                         |     |          |                      |                          |              |
|`Attendant Routing`              |Y                         |Y                        |Y    |Y         |Y                     |Y                         |*既定値*     |
|`Longest Idle`<sup>3</sup>       |Y                         |Y                        |N    |Y         |Y                     |Y                         |*推奨* |
|`Round Robin`                    |Y                         |Y                        |Y    |Y         |Y                     |Y                         |*推奨* |
|`Serial`                         |Y                         |Y                        |Y    |Y         |Y4<sup></sup>         |Y4<sup></sup>             |              |
|**転送モード**               |                          |                         |     |          |                      |                          |              |
|`Conference Mode`<sup>5</sup>    |Y                         |Y                        |N    |Y6<sup></sup>|Y                  |Y                         |*推奨* |
|`Transfer Mode`                  |Y                         |Y                        |Y    |Y         |Y                     |Y                         |              |
|プレゼンス ベースのルーティング<sup>3</sup>|Y                        |Y                        |N    |Y         |Y                     |Y                         |*推奨* |
|エージェントはオプトアウトできます               |Y                         |Y                        |Y7<sup></sup>|Y7<sup></sup>|Y          |Y                         |*既定値*     |
|チャネル ベースのキュー             |Y                         |N                        |N    |N         |n/a                   |Y8<sup></sup>             |              |
|呼び出しトーストにリソース アカウント名が表示される |Y9<sup></sup>       |Y                        |Y    |          |Y                     |Y                         |              |
|**動的呼び出し元 ID**            |                          |                         |     |          |                      |                          |              |
|`Standard call queue`            |N                         |N                        |N    |N         |Y                     |n/a                       |              |
|`Channel based call queue`       |Y                         |n/a                      |n/a  |n/a       |n/a                   |Y                         |              |
|**PSTN 接続方法**    |                          |                         |     |          |                      |                          |「注 10」を参照してください。   |
|`Calling Plans`                  |Y                         |Y                        |Y    |Y         |Y                     |Y                         |              |
|`Direct Routing`                 |Y                         |Y                        |N    |N         |Y                     |Y                         |              |
|`Operator Connect`               |Y                         |Y                        |     |          |Y                     |Y                         |              |

注:
1. Microsoft Teams Windowsクライアント、Microsoft Teams Mac クライアント、仮想デスクトップ インフラストラクチャMicrosoft Teams Web クライアントMicrosoft Teamsを使用します。
2. Microsoft Teams iPhone、Android Microsoft Teamsアプリ。
3. エージェント ルーティング方法で [最長アイドル] を選択すると、プレゼンス ベースのルーティングが自動的に有効になります。
4. 標準の通話キューの一部として個々のユーザーを追加する場合にのみ、順序を設定できます。 配布リストまたは配布チャネルが使用Teams順序はアルファベット順です。
5. 電話呼び出しが、場所ベースのルーティングが有効になっているダイレクト ルーティング ゲートウェイからキューにルーティングされる場合、電話会議モードはサポートされません。
6. Microsoft Teams電話のみ。
7. [User 設定 ポータル] ページを使用します。https://aka.ms/vmsettings
8. サポートされているのはパブリック チャネルのみです。
9. Web Teamsを除外します。
10. 自動応答と通話キューでは、PSTN 接続方法間で通話を転送できません。


## <a name="supported-clients"></a>サポートされるクライアント

呼び出しキュー内の呼び出しエージェントでは、次のクライアントがサポートされます。

  - Skype for Business クライアント 2016 (32 ビット版と 64 ビット版)
  - Lync デスクトップ クライアント 2013 (32 ビット版と 64 ビット版)
  - すべての IP 電話モデルは、Microsoft Teams。 「[Getting phones for Skype for Business Online」を参照してください](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
  - Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)
  - Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)
  - iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)
  - Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)
  - Microsoft Teams Windows クライアント (32 ビットおよび 64 ビット バージョン)
  - Microsoft Teams Mac クライアント
  - Microsoft Teams[デスクトップ インフラストラクチャ](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop、Citrix、VMware) に関するページ
  - Microsoft Teams iPhone アプリ
  - Microsoft Teams Android アプリ

    > [!NOTE]
    > 直接ルーティング番号が割り当てられた通話キューは、クライアント、Lync Skype for Business、または IP Phone をエージェントとしてSkype for Businessをサポートしません。 このTeamsクライアントは、共同存在モードでのみサポートされ、Teams[されます](/microsoftteams/setting-your-coexistence-and-upgrade-settings)。

## <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

Windows PowerShellでは、コマンド ラインを使用して、バッチまたはプログラムで呼び出しキューを作成および管理できます。

次のコマンドレットを使用すると、呼び出しキューを管理できます。

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

ユーザー、リソース アカウント、Microsoft Teams 電話 ライセンス、電話番号、オーディオ ファイル、および呼び出しキューで使用されるサポートされている言語を管理するには、次の追加のコマンドレットも必要です。

Users/Teams

- ユーザー
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)
- - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

リソース アカウント:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

仮想Teams 電話 ライセンス:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

電話の割り当て:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-csphonenumberassignment)

オーディオ ファイル

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

サポート言語リスト

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)

PowerShell を使用して呼び出しキューを作成する手順については、「PowerShell コマンドレットを使用した通話キューの [作成」を参照してください。](create-a-phone-system-call-queue-via-cmdlets.md)

## <a name="call-queue-diagnostic-tool"></a>キュー診断ツールの呼び出し

管理者の場合は、次の診断ツールを使用して、通話キューが通話を受信できると検証できます。

1. 以下の **[テストの実行]** を選択すると、診断が Microsoft 365 管理センターに表示されます。 

   > [!div class="nextstepaction"]
   > [テストの実行: Teams 呼び出しキュー](https://aka.ms/TeamsCallQueueDiag)

2. [診断の実行] ウィンドウで、[ユーザー名] フィールドまたは [電子メール] フィールドにリソース アカウント **を** 入力し、[テストの実行] **を選択します**。

3. このテストでは、テナント、ポリシー、リソース アカウントの構成に対処して、呼び出しキューが呼び出しを受信できると検証するための最適な次の手順が返されます。

## <a name="related-topics"></a>関連項目

[次の方法で利用Microsoft Teams 電話](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
