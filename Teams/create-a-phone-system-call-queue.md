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
description: Microsoft Teams で通話キュー用の電話システムをセットアップする方法について説明します。応答メッセージの提供、音楽の保留、通話リダイレクト、その他の機能が提供されます。
ms.openlocfilehash: d696b37f95d06c529aa330bd77e2ec91e1ffc9ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49765340"
---
# <a name="create-a-call-queue"></a>呼び出しキューを作成する

通話キューは、組織内の特定の問題や質問に役立つユーザーに発信者をルーティングする方法を提供します。 通話はキュー内のユーザー (エージェントと呼ばれる) に一度に 1 つ配布 *されます*。 

通話キューには次の機能があります。

- あいさつメッセージ。

- ユーザーがキューで保留を待っている間の音楽。

- コール ルーティング - *First In、First Out* (FIRST Out )順序で- エージェントに。

- キュー オーバーフローとタイムアウトの処理オプション。

この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)の自動応答と通話キューの[](plan-auto-attendant-call-queue.md#getting-started)計画」を読み、開始手順に従ってください。

通話キューを設定するには、Teams 管理センターで [音声] を展開し、[通話キュー] をクリックして、[追加] をクリック **します**。

## <a name="resource-account-and-language"></a>リソース アカウントと言語

![リソース アカウントと言語設定のスクリーンショット](media/call-queue-name-language.png)

1. 通話キューの名前を入力します。 エージェントは、キューからの着信通話を受信すると、この名前を表示します。

2. [**アカウントの追加]** をクリックし、この通話キューで使用するリソース アカウントを検索し、[追加] をクリックして、[追加] をクリック **します**。

3. 言語を選択します。 この言語は、システム生成の音声プロンプトとボイスメール トランスクリプション (有効にした場合) に使用されます。

## <a name="greetings-and-music-on-hold-in-queue"></a>キュー内の応答メッセージと保留音

発信者がキューに入った場合に発信者に応答メッセージを再生する場合に指定します。 再生する応答メッセージを含む MP3、WAV、または WMA ファイルをアップロードする必要があります。

Teams は、キューで保留にしている間、発信者に既定の音楽を提供します。 特定のオーディオ ファイルを再生する場合は、[オーディオ ファイルの再生] を選択し、MP3、WAV、または WMA ファイルをアップロードします。

> [!NOTE]
> アップロードされた記録は 5 MB 以下にできます。
> Teams の通話キューで提供される既定の音楽には、組織が支払う料金は無料です。 

## <a name="call-agents"></a>コール エージェント

エージェントを通話キュー [に](plan-auto-attendant-call-queue.md#prerequisites) 追加するには、「前提条件」を参照してください。

![通話キューのユーザーとグループの設定のスクリーンショット](media/call-queue-users-groups.png)

最大 20 人のエージェントを個別に追加し、最大 200 人のエージェントをグループ経由で追加できます。

キューにユーザーを追加するには、[ユーザーの追加] をクリックし、ユーザーを検索し、[追加] をクリックして、[追加] をクリック **します**。

キューにグループを追加するには、[グループの追加] をクリックし、グループを検索し、[追加] をクリックして、[追加] をクリック **します**。 配布リスト、セキュリティ グループ、Microsoft 365 グループまたは Microsoft Teams チームを使用できます。

> [!NOTE]
> グループに追加された新しいユーザーは、最初の通話が到着するために最大 8 時間かかる場合があります。

## <a name="call-routing"></a>通話ルーティング

![電話会議モードとルーティング方法の設定のスクリーンショット](media/call-queue-conference-mode-routing-method.png)

**電話会議モード** では、エージェントが通話を受け入れてから、発信者がエージェントに接続するのにかかる時間が大幅に短縮されます。 会議モードが機能するには、通話キュー内のエージェントが次のいずれかのクライアントを使用する必要があります。

  - 最新バージョンの Microsoft Teams デスクトップ クライアント、Android アプリ、または iOS アプリ
  - Microsoft Teams の電話バージョン 1449/1.0.94.2020051601 以降
  
エージェントの Teams アカウントは、Teams 専用モードに設定する必要があります。 要件を満たしていないエージェントは、通話ルーティング リストに含まれません。 エージェント全員が互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。

> [!NOTE]
> 取り込み中の取り込み中は、電話会議モードではサポートされていません。 プレゼンス ベースのルーティングが有効になっていない場合、非通話キュー呼び出しのエージェントは通話キューの呼び出しで引き続き表示される場合があります。

**ルーティング方法は** 、エージェントがキューから通話を受信する順序を決定します。 次のオプションから選択します。

- **アテンダント** ルーティングでは、キュー内のすべてのエージェントが同時に呼び出されます。 通話を受け取る最初の通話エージェントが通話を受け取る。

- **シリアル ルーティングは** 、すべてのコール エージェントを、コール エージェント リストで指定された順序で 1 **つ 1 つリング** します。 エージェントが通話を却下するか、通話を受け取らない場合、通話は次のエージェントを呼び出し、エージェントが受け取されるか、または時間が切れるまですべてのエージェントを試します。

- **ラウンド ロビンは** 、着信通話のルーティングのバランスを取り、各通話エージェントがキューから同じ数の通話を受け取ります。 受信販売環境では、すべてのコール エージェント間で機会が均等に確保されるのが望ましい場合があります。

- **アイドル時間が** 最も長いエージェントに各呼び出しがルーティングされます。 エージェントのプレゼンス状態が [使用可能] の場合、またはプレゼンス状態が 10 分未満の場合、エージェントはアイドルと見なされます。 プレゼンス状態が 10 分以上離れたエージェントはアイドルと見なされ、プレゼンスを [利用可能] に変更するまで通話を受信できません。 

![ルーティング、オプトアウト、通知時間の設定のスクリーンショット](media/call-queue-presence-agents-time.png)


**プレゼンス ベースのルーティング** では、エージェントの可用性の状態を使用して、選択したルーティング方法の通話ルーティング リストにエージェントを含める必要があるかどうかを決定します。 利用可能状態が [連絡可能]に設定されているコール エージェントは、通話ルーティング リストに含まれており、通話を受信できます。 利用可能状態が他の状態に設定されているエージェントは、通話ルーティング リストから除外され、利用可能状態が [連絡可能] に戻るまで通話を受信 **しません**。 

プレゼンス ベースの通話ルーティングは、任意のルーティング方法で有効にできます。

エージェントが通話の受け取りをオプトアウトした場合、エージェントの状態に設定されている状態に関係なく、エージェントは通話ルーティング リストに含まれません。 

> [!NOTE]
> プレゼンス ベースのルーティングが有効な場合、Skype for Business クライアントを使用するエージェントは通話ルーティング リストに含まれません。 Skype for Business を使用するエージェントが存在する場合は、プレゼンス ベースの通話ルーティングを有効にしない。

**エージェント通知時間は** 、キューが呼び出しを次のエージェントにリダイレクトする前にエージェントの電話が鳴る時間を指定します。

大ボリューム キューの場合は、次の設定をお勧めします。

- **会議モードから****自動へ**
- **Attendant ルーティングへの****ルーティング方法**
- **プレゼンス ベースの [オン]** **へのルーティング**
- **エージェントの通知時間:** **20 秒**

## <a name="call-overflow-handling"></a>呼び出しオーバーフロー処理

![呼び出しオーバーフロー設定のスクリーンショット](media/call-queue-overflow-handling.png)

**キュー内の最大呼び** 出し数は、任意の時点でキュー内で待機できる呼び出しの最大数を指定します。 既定値は 50 ですが、0 から 200 の範囲で指定できます。 この制限に達すると、呼び出しは [通話の最大数に達した場合] 設定で指定された方法 **で処理** されます。

通話を切断するか、任意の通話ルーティング先にリダイレクトすることができます。 たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。 外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)番号の書式設定の技術的な詳細」を参照してください。

> [!NOTE]
> 通話の最大数が 0 に設定されている場合、あいさつメッセージは再生されません。

## <a name="call-timeout-handling"></a>通話のタイムアウト処理

![通話タイムアウト設定のスクリーンショット](media/call-queue-timeout-handling.png)

**通話タイムアウト: 最大待ち** 時間は、呼び出しがリダイレクトまたは切断される前にキュー内で保留にできる最大時間を指定します。 0 秒から 45 分の値を指定できます。

通話を切断するか、通話ルーティング先の 1 つにリダイレクトすることができます。 たとえば、発信者にキュー内のエージェントのボイスメールを残す場合があります。 外部転送については、「前提条件」と[](plan-auto-attendant-call-queue.md#prerequisites)「外部電話番号の転送[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)番号の書式設定の技術的な詳細」を参照してください。

通話のタイムアウト オプションを選ぶと、[保存] をクリック **します**。

## <a name="caller-id-for-outbound-calls"></a>発信通話の発信者番号

通話キュー内のエージェントがダイヤルアウトして顧客の通話を返す可能性がある場合は、通話キューのメンバーの発信者番号を適切な自動応答のサービス番号に設定する方法を検討してください。 詳細 [については、「Microsoft Teams で発信者番号ポリシーを](caller-id-policies.md) 管理する」を参照してください。

## <a name="supported-clients"></a>サポートされるクライアント

通話キュー内のコール エージェントでは、次のクライアントがサポートされます。

  - Skype for Business デスクトップ クライアント 2016 (32 ビット版と 64 ビット版)
  - Lync デスクトップ クライアント 2013 (32 ビット版と 64 ビット版)
  - Microsoft Teams でサポートされるすべての IP 電話モデル。 [「Skype for Business Online の電話を取得する」を参照してください](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
  - Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)
  - Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)
  - iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)
  - Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)
  - Microsoft Teams Windows クライアント (32 ビット版と 64 ビット版)
  - Microsoft Teams Mac クライアント
  - Microsoft Teams iPhone アプリ
  - Microsoft Teams Android アプリ

    > [!NOTE]
    > 直接ルーティング番号が割り当てられている通話キューは、エージェントとして Skype for Business クライアント、Lync クライアント、または Skype for Business IP Phone をサポートしません。

## <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

Windows PowerShell を使用して通話キューを作成し、設定することもできます。 通話キューの管理に使用するコマンドレットを次に示します。

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>関連トピック

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
