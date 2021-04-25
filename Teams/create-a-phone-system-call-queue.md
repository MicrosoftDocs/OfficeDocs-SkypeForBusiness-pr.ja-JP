---
title: Microsoft Teams で通話キューを作成する
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
description: Microsoft Teams を使用して通話キュー用の電話システムを設定する方法について説明します。これは、案内メッセージ、保留音楽、通話リダイレクト、その他の機能を提供します。
ms.openlocfilehash: f60714bc1c4868496209f414583c925da527460a
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995285"
---
# <a name="create-a-call-queue"></a>呼び出しキューを作成する

通話キューは、特定の問題や質問に役立つ組織内のユーザーに発信者をルーティングする方法を提供します。 呼び出しは、キュー内のユーザー (エージェントと呼ばれる) に一度に 1 回配布 *されます*。 

呼び出しキューには、次の機能が提供されます。

- あいさつメッセージ。

- ユーザーがキューで保留を待機している間の音楽。

- 通話ルーティング - *First In、First Out* (FIFO) の順序でエージェントに送信します。

- キュー オーバーフローとタイムアウトの処理オプション。

この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)の自動応答と通話キューの[](plan-auto-attendant-call-queue.md#getting-started)計画」を読み、開始手順に従ってください。

通話キューを設定するには、Teams 管理センターで [Voice] を展開し、[通話キュー] をクリックし、[追加] を **クリックします**。 

## <a name="resource-account-and-language"></a>リソース アカウントと言語

![リソース アカウントと言語設定のスクリーンショット](media/call-queue-name-language.png)

1. 呼び出しキューの名前を入力します。

2. [**アカウントの追加]** をクリックし、この呼び出しキューで使用するリソースアカウントを検索し、[追加] をクリックし、[追加] を **クリックします**。 (エージェントは、着信呼び出しを受信すると、リソース アカウント名が表示されます)。

3. サポートされている言語 [を選択します](create-a-phone-system-call-queue-languages.md)。 この言語は、システムで生成された音声プロンプトとボイスメールの文字起こし (有効にした場合) に使用されます。

## <a name="greetings-and-music-on-hold-in-queue"></a>キュー内のグリーティングと保留の音楽

発信者がキューに到着するときに、発信者にあいさつを再生する場合に指定します。 再生するあいさつを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。

Teams は、キューで保留の間、呼び出し元に既定の音楽を提供します。 特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。

> [!NOTE]
> アップロードされた記録は、5 MB 以下に設定できます。
> Teams 呼び出しキューで提供される既定の音楽には、組織が支払うロイヤリティは無料です。 

## <a name="call-agents"></a>エージェントを呼び出す

エージェントを [呼び出しキューに追加するための前提条件を確認します](plan-auto-attendant-call-queue.md#prerequisites)。

![通話キューのユーザーとグループの設定のスクリーンショット](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Teams チャネル

Teams チャネルを使用して最大 200 人のエージェントを追加できます。

Teams チャネルを使用 [してキューを](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)管理する場合は、[チームの選択] オプションを選択し、[チャネルの追加 **] をクリックします**。 使用するチームを検索して選択し、[追加] を **クリックします**。 使用するチャネルを選択し、[適用] を **クリックします**。

次のクライアントは、通話キューに Teams チャネルを使用する場合にサポートされます。 

  - Microsoft Teams Windows クライアント
  - Microsoft Teams Mac クライアント

##### <a name="users-and-groups"></a>ユーザーとグループ

最大 20 人のエージェントを個別に追加し、最大 200 人のエージェントをグループ経由で追加できます。

キューに個々のユーザーまたはグループを追加する場合は、[ユーザーとグループの選択] オプション **を選択** します。 

キューにユーザーを追加するには、[ユーザーの追加] をクリックし、ユーザーを検索し、[追加] をクリックし、[追加] を **クリックします**。

キューにグループを追加するには、[グループの追加] をクリックし、グループを検索し、[追加] をクリックし、[追加] を **クリックします**。 配布リスト、セキュリティ グループ、および Microsoft 365 グループまたは Microsoft Teams チームを使用できます。

> [!NOTE]
> グループに追加された新しいユーザーは、最初の呼び出しが到着するために最大 8 時間かかる場合があります。

## <a name="call-routing"></a>通話ルーティング

![会議モードとルーティング方法の設定のスクリーンショット](media/call-queue-conference-mode-routing-method.png)

**会議モード** では、エージェントが呼び出しを受け入れる後に、呼び出し元がエージェントに接続するのにかかる時間が大幅に短縮されます。 会議モードを機能するには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。

  - Microsoft Teams デスクトップ クライアント、Android アプリ、または iOS アプリの最新バージョン
  - Microsoft Teams の電話バージョン 1449/1.0.94.2020051601 以降
  
エージェントの Teams アカウントは、Teams 専用モードに設定する必要があります。 要件を満たしていないエージェントは、通話ルーティング リストに含まれません。 エージェントが互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。

> [!NOTE]
> 場所に基づくルーティングが有効になっているダイレクト ルーティング ゲートウェイから電話がキューにルーティングされる場合、会議モードはサポートされません。

**ルーティング方法は** 、エージェントがキューから呼び出しを受信する順序を決定します。 次のオプションから選択します。

- **アテンダント ルーティング** では、キュー内のすべてのエージェントが同時に呼び出されます。 呼び出しを受け取る最初の呼び出しエージェントは、呼び出しを取得します。

- **シリアル ルーティングでは** 、すべての呼び出しエージェントが[エージェントの呼び出し] リストで指定された順序 **で 1 つ 1 つリング** されます。 エージェントが通話を却下または取り上げない場合、呼び出しは次のエージェントを呼び出し、そのエージェントが取り上げられるか、または時間が切れるまですべてのエージェントを試します。

- **ラウンド ロビンは** 、着信呼び出しのルーティングのバランスを取り、各呼び出しエージェントがキューから同じ数の呼び出しを取得します。 これは、すべての通話エージェント間で均等な機会を確保するために、受信販売環境で望ましい場合があります。

- **アイドル時間が** 最も長いエージェントに各呼び出しがルーティングされます。 エージェントのプレゼンス状態が [使用可能] である場合、またはプレゼンス状態が 10 分未満離れた場合、エージェントはアイドル状態と見なされます。 プレゼンス状態が 10 分以上離れたエージェントはアイドル状態とは見なされません。プレゼンスを [利用可能] に変更するまで、通話を受信する資格は得られません。 

![ルーティング、オプトアウト、アラート時間の設定のスクリーンショット](media/call-queue-presence-agents-time.png)


**プレゼンス ベースのルーティングでは** 、呼び出しエージェントの可用性状態を使用して、エージェントを選択したルーティング方法の呼び出しルーティング リストに含める必要があるかどうかを判断します。 可用性の状態が [利用可能] に設定されている通話エージェント **は、通話** ルーティング リストに含まれており、呼び出しを受信できます。 可用性の状態が他の状態に設定されているエージェントは、通話ルーティング リストから除外され、可用性の状態が [利用可能] に戻るまで呼び出しを受信 **しません**。 

任意のルーティング方法でプレゼンス ベースの呼び出しルーティングを有効にできます。

エージェントが通話の受け取りをオプトアウトした場合、エージェントの可用性の状態が設定されている状況に関係なく、通話ルーティング リストに含まれません。 

> [!NOTE]
> プレゼンス ベースのルーティングが有効になっている場合、Skype for Business クライアントを使用するエージェントは、通話ルーティング リストに含まれません。 Skype for Business を使用するエージェントがある場合は、プレゼンス ベースの通話ルーティングを有効にしない。

**エージェントアラート時間は** 、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。

次の設定をお勧めします。

- **会議モードを** [自動] **に設定する**
- **ラウンド ロビンまたは****最長アイドルへの****ルーティング方法**
- **プレゼンス ベースのルーティングを** **On に設定する**
- **エージェントのアラート時間:** **20 秒**

> [!NOTE]
> プレゼンス ベースのルーティングが有効ではなく、キュー内に複数の呼び出しがある場合、システムはプレゼンス状態に関係なく、これらの呼び出しをエージェントに同時に表示します。 これにより、エージェントに対して複数の通話通知が送信されます。特に、一部のエージェントがエージェントに提示された最初の呼び出しに応答しない場合。

## <a name="call-overflow-handling"></a>呼び出しオーバーフロー処理

![呼び出しオーバーフロー設定のスクリーンショット](media/call-queue-overflow-handling.png)

**キュー内の最大呼び** 出し数は、任意の時点でキューで待機できる呼び出しの最大数を指定します。 既定値は 50 ですが、0 から 200 の範囲で指定できます。 この制限に達すると、呼び出しは [呼び出しの最大数に達した場合] 設定で指定された通 **り処理** されます。

通話を切断するか、任意の呼び出しルーティング先にリダイレクトすることができます。 たとえば、発信者がキュー内のエージェントのボイスメールを残す場合があります。 外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)番号の書式設定に関する技術的な詳細」を参照してください。

> [!NOTE]
> 呼び出しの最大数が 0 に設定されている場合、あいさつメッセージは再生されません。

## <a name="call-timeout-handling"></a>呼び出しタイムアウト処理

![通話タイムアウト設定のスクリーンショット](media/call-queue-timeout-handling.png)

**呼び出しタイムアウト:** 最大待機時間は、呼び出しがリダイレクトまたは切断される前にキューで保留にできる最大時間を指定します。 0 秒から 45 分の値を指定できます。

通話を切断するか、または呼び出しルーティング先の 1 つにリダイレクトすることができます。 たとえば、発信者がキュー内のエージェントのボイスメールを残す場合があります。 外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)番号の書式設定に関する技術的な詳細」を参照してください。

通話タイムアウト オプションを選択した場合は、[保存] を **クリックします**。

## <a name="caller-id-for-outbound-calls"></a>発信呼び出しの呼び出し元 ID

通話キュー内のエージェントがダイヤルアウトして顧客の通話を返す場合があります。通話キューのメンバーの発信者 ID を、適切な自動応答のサービス番号に設定してください。 詳細については [、「Microsoft Teams で発信者 ID ポリシーを管理する」](caller-id-policies.md) を参照してください。

## <a name="supported-clients"></a>サポートされるクライアント

呼び出しキューの呼び出しエージェントでは、次のクライアントがサポートされます。

  - Skype for Business デスクトップ クライアント 2016 (32 ビット版と 64 ビット版)
  - Lync デスクトップ クライアント 2013 (32 ビット版と 64 ビット版)
  - Microsoft Teams でサポートされているすべての IP フォン モデル。 「Skype for Business [Online の電話を取得する」を参照してください](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
  - Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)
  - Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)
  - iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)
  - Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)
  - Microsoft Teams Windows クライアント (32 ビット版と 64 ビット版)
  - Microsoft Teams Mac クライアント
  - Microsoft Teams on [Virtualed Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop、Citrix、VMware)
  - Microsoft Teams iPhone アプリ
  - Microsoft Teams Android アプリ

    > [!NOTE]
    > 直接ルーティング番号が割り当てられている通話キューは、Skype for Business クライアント、Lync クライアント、または Skype for Business IP Phone をエージェントとしてサポートしません。

## <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

Windows PowerShell を使用して通話キューを作成し、設定することもできます。 呼び出しキューの管理に使用するコマンドレットを次に示します。

- [New-CsCallQueue](/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>関連項目

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance)

[Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
