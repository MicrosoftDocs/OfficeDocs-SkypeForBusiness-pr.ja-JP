---
title: 呼び出しキューを作成Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Microsoft Teams を使用して通話キューの 電話システム を設定する方法について説明します。この機能では、あいさつメッセージ、保留音、通話リダイレクトなどの機能が提供されます。
ms.openlocfilehash: 8b4fe4283ac9734c1dc29bf33759039098578744
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064803"
---
# <a name="create-a-call-queue"></a>呼び出しキューを作成する

通話キューは、特定の問題や質問に役立つ組織内のユーザーに発信者をルーティングする方法を提供します。 呼び出しは、キュー内のユーザー (エージェントと呼ばれる) に一度に 1 回 *配布されます*。 

呼び出しキューには、次の機能があります。

- あいさつメッセージ。

- ユーザーがキューで保留を待機している間の音楽。

- コール ルーティング - *First In,First Out* (FIFO) order - to agents.

- キューのオーバーフローとタイムアウトの処理オプション。

この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)自動応答と通話キューの計画」を[](plan-auto-attendant-call-queue.md#getting-started)読み、概要の手順に従ってください。

通話キューを設定するには、Teams 管理センターで、[音声] を展開し、[通話キュー] をクリックし、[追加] を **クリックします**。

## <a name="video-demonstration"></a>ビデオデモ

このビデオでは、通話キューを作成する方法の基本的な例をTeams。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="resource-account-and-language"></a>リソース アカウントと言語

![リソース アカウントと言語設定のスクリーンショット](media/call-queue-name-language.png)

1. 通話キューの名前を入力します。

2. [**アカウントの追加]** をクリックし、この呼び出しキューで使用するリソースアカウントを検索し、[追加] をクリックして、[追加] を **クリックします**。 (エージェントは、着信呼び出しを受信すると、リソース アカウント名を表示します)。

3. サポートされている [言語を選択します](create-a-phone-system-call-queue-languages.md)。 この言語は、システムで生成された音声プロンプトとボイスメールのトランスクリプション (有効にした場合) に使用されます。

## <a name="greetings-and-music-on-hold-in-queue"></a>キュー内の応答メッセージと保留音

発信者がキューに到着するときに、発信者にあいさつメッセージを再生する場合に指定します。 再生するあいさつメッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。

Teamsキュー内で保留されている間、呼び出し元に既定の音楽を提供します。 特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。

> [!NOTE]
> アップロードされた記録は 5 MB 以下にできます。
> 通話キューで提供される既定Teamsは、組織が支払う使用料金は無料です。 

## <a name="call-agents"></a>エージェントの呼び出し

エージェントを [呼び出しキューに追加するための前提条件を確認します](plan-auto-attendant-call-queue.md#prerequisites)。

![通話キューのユーザーとグループの設定のスクリーンショット](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Teams チャネル

1 つのチャネルを介して最大 200 のエージェントTeamsできます。

キューを管理するために [Teamsを使用する](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)場合は、[チームの選択] オプションを選択し、[チャネルの追加 **] をクリックします**。 使用するチームを検索して選択し、[追加] を **クリックします**。 使用するチャネルを選択し、[適用] を **クリックします**。

次のクライアントは、呼び出しキューにTeamsチャネルを使用する場合にサポートされます。 

  - Microsoft Teams Windows クライアント
  - Microsoft Teams Mac クライアント

##### <a name="users-and-groups"></a>ユーザーとグループ

最大 20 個のエージェントを個別に追加し、最大 200 個のエージェントをグループ経由で追加できます。

キューに個々のユーザーまたはグループを追加する場合は、[ユーザーとグループの選択 **] オプションを選択** します。 

キューにユーザーを追加するには、[ユーザーの追加]**をクリック** し、ユーザーを検索し、[追加] をクリックして、[追加] を **クリックします**。

キューにグループを追加するには、[グループの追加]**をクリック** し、グループを検索し、[追加] をクリックして、[追加] を **クリックします**。 配布リスト、セキュリティ グループ、およびグループまたはチームMicrosoft 365使用Microsoft Teamsできます。

> [!NOTE]
> グループに追加された新しいユーザーは、最初の呼び出しが到着するために最大 8 時間かかる場合があります。

## <a name="call-routing"></a>通話ルーティング

![電話会議モードとルーティング方法の設定のスクリーンショット](media/call-queue-conference-mode-routing-method.png)

**電話会議モード** では、エージェントが呼び出しを受け入れてから、呼び出し元がエージェントに接続するのにかかる時間が大幅に短縮されます。 電話会議モードを機能するには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。

  - デスクトップ クライアント、Android Microsoft Teams iOS アプリの最新バージョン
  - Microsoft Teamsバージョン 1449/1.0.94.2020051601 以降
  
エージェントのTeamsアカウントは、Teamsモードに設定する必要があります。 要件を満たしていないエージェントは、通話ルーティングの一覧には含まれません。 エージェントが互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。

> [!NOTE]
> 電話呼び出しが、場所ベースのルーティングが有効になっているダイレクト ルーティング ゲートウェイからキューにルーティングされる場合、電話会議モードはサポートされません。

**ルーティング方法は** 、エージェントがキューから呼び出しを受信する順序を決定します。 次のオプションから選択します。

- **アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。 呼び出しを受け取る最初の呼び出しエージェントが呼び出しを取得します。

- **シリアル ルーティングでは** 、すべての呼び出しエージェントが[通話エージェント] の一覧で指定された順序 **で 1 つ 1 つリング** されます。 エージェントが通話を閉じ、または呼び出しを受け取らない場合、呼び出しは次のエージェントを呼び出し、エージェントが取り出されるか、または時間が切れるまですべてのエージェントを試します。

- **ラウンド ロビンは** 、着信呼び出しのルーティングのバランスを取り、各呼び出しエージェントがキューから同じ数の呼び出しを取得します。 これは、すべての通話エージェント間で均等な機会を確保するために、受信販売環境で望ましい場合があります。

- **アイドル時間が** 最も長いエージェントに各呼び出しをルーティングします。 エージェントのプレゼンス状態が [使用可能] の場合、またはプレゼンス状態が 10 分未満の場合、エージェントはアイドル状態と見なされます。 プレゼンス状態が 10 分を超える状態のエージェントはアイドル状態とは見なされません。プレゼンスを [利用可能] に変更するまで、通話を受信する資格は得られません。 

![ルーティング、オプトアウト、アラート時間の設定のスクリーンショット](media/call-queue-presence-agents-time.png)


**プレゼンス ベースのルーティングでは** 、呼び出しエージェントの可用性状態を使用して、選択したルーティング方法の呼び出しルーティング リストにエージェントを含める必要があるかどうかを判断します。 可用性の状態が [使用可能] に設定されている通話エージェント **は、通話** ルーティング リストに含まれており、通話を受信できます。 可用性の状態が他の状態に設定されているエージェントは、通話ルーティング リストから除外され、可用性の状態が [利用可能] に戻るまで、呼び出しを受信 **しません**。 

プレゼンス ベースの呼び出しルーティングは、任意のルーティング方法で有効にできます。

エージェントが呼び出しを受け取らない場合、エージェントは、可用性の状態が設定されているに関係なく、通話ルーティング リストに含まれません。 

> [!NOTE]
> プレゼンス ベースのルーティングSkype for Business、クライアントを使用するエージェントは、呼び出しルーティング の一覧に含まれません。 このサービスを使用するエージェントSkype for Business、プレゼンス ベースの呼び出しルーティングを有効にすることはできません。

**エージェント アラート時間は** 、キューが呼び出しを次のエージェントにリダイレクトする前に、エージェントの電話が鳴る時間を指定します。

次の設定をお勧めします。

- **会議モードから****自動**
- **ラウンド ロビンまたは****最長アイドルへの****ルーティング方法**
- **プレゼンス ベースのルーティングを** **[オン] に設定する**
- **エージェントのアラート時間:** **~ 20 秒**

> [!NOTE]
> プレゼンス ベースのルーティングが有効ではなく、キュー内に複数の呼び出しがある場合、システムは、プレゼンス状態に関係なく、これらの呼び出しをエージェントに同時に表示します。 これにより、エージェントに対する複数の呼び出し通知が発生します。特に、一部のエージェントがエージェントに提示された最初の呼び出しに応答しない場合。

## <a name="call-overflow-handling"></a>呼び出しオーバーフロー処理

![呼び出しオーバーフロー設定のスクリーンショット](media/call-queue-overflow-handling.png)

**キュー内の最大呼び** 出し数は、特定の時点でキュー内で待機できる呼び出しの最大数を指定します。 既定値は 50 ですが、0 ~ 200 の範囲で指定できます。 この制限に達すると、呼び出しは [呼び出しの最大数に達した場合] 設定で指定された **方法で処理** されます。

通話を切断するか、任意の通話ルーティング先にリダイレクトすることができます。 たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。 外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送 - 番号の書式設定に関[する技術的な詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)」を参照してください。

> [!NOTE]
> 呼び出しの最大数が 0 に設定されている場合、あいさつメッセージは再生されません。

## <a name="call-timeout-handling"></a>呼び出しタイムアウト処理

![通話タイムアウト設定のスクリーンショット](media/call-queue-timeout-handling.png)

**呼び出** しタイムアウト: 最大待機時間は、呼び出しがリダイレクトまたは切断される前にキューで保留にできる最大時間を指定します。 0 秒から 45 分の値を指定できます。

通話を切断するか、または通話ルーティング先の 1 つにリダイレクトすることができます。 たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。 外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送 - 番号の書式設定に関[する技術的な詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)」を参照してください。

通話タイムアウト オプションを選択した後、[保存] を **クリックします**。

## <a name="caller-id-for-outbound-calls"></a>発信呼び出しの呼び出し元 ID

通話キュー内のエージェントはダイヤルアウトして顧客の通話を返す可能性があります。通話キューのメンバーの発信者番号を適切な自動応答のサービス番号に設定します。 詳細[については、「Microsoft Teams で](caller-id-policies.md)発信者番号ポリシーを管理する」を参照してください。

## <a name="supported-clients"></a>サポートされるクライアント

呼び出しキュー内の呼び出しエージェントでは、次のクライアントがサポートされます。

  - Skype for Business クライアント 2016 (32 ビット版と 64 ビット版)
  - Lync デスクトップ クライアント 2013 (32 ビット版と 64 ビット版)
  - すべての IP 電話モデルは、Microsoft Teams。 [「Getting phones for Skype for Business Online 」を参照してください](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
  - Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)
  - Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)
  - iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)
  - Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)
  - Microsoft Teams Windows クライアント (32 ビットおよび 64 ビット バージョン)
  - Microsoft Teams Mac クライアント
  - Microsoft Teams[デスクトップ インフラストラクチャ](/microsoftteams/teams-for-vdi)(Windows Virtual Desktop、Citrix、VMware) に関するページ
  - Microsoft Teams iPhone アプリ
  - Microsoft Teams Android アプリ

    > [!NOTE]
    > 直接ルーティング番号が割り当てられた通話キューは、クライアント、Lync クライアント、Skype for Business IP Phone をエージェントSkype for Businessサポートしません。

## <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

Windows PowerShell を使用して通話キューを作成し、設定することもできます。 呼び出しキューの管理に使用するコマンドレットを次に示します。

- [New-CsCallQueue](/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>関連トピック

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance)

[Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
