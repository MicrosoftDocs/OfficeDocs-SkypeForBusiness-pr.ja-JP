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
description: Microsoft Teams で通話キューの電話システムをセットアップする方法について説明します。これにより、グリーティングメッセージの送信、音楽の保留、リダイレクト、その他の機能を行うことができます。
ms.openlocfilehash: fb4510ce81b09569a8228916b7d05cc6697caac8
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49089328"
---
# <a name="create-a-call-queue"></a>呼び出しキューを作成する

通話キューには、特定の問題や質問について支援できる組織内のユーザーに、発信者をルーティングする方法が用意されています。 通話は、キュー内のユーザー ( *エージェント* と呼ばれます) に一度に1つずつ配布されます。 

通話キューでは次の情報を提供します。

- あいさつメッセージ。

- 他のユーザーがキューで待機中の音楽

- *まず、* ルーティング先 (FIFO) の順に呼び出します。

- キューのオーバーフローとタイムアウトのオプション。

この記事に記載されている手順を実行する前に、「 [Teams の自動応答と通話キューのプラン](plan-auto-attendant-call-queue.md) 」を参照し、 [作業の開始の手順](plan-auto-attendant-call-queue.md#getting-started) に従っていることを確認してください。

通話キューを設定するには、Teams 管理センターで、[ **音声**]、[ **通話キュー**] の順に展開し、[ **追加**] をクリックします。

## <a name="resource-account-and-language"></a>リソースアカウントと言語

![リソースのアカウントと言語の設定のスクリーンショット](media/call-queue-name-language.png)

1. 通話キューの名前を入力します。 キューからの着信通話を受信すると、エージェントはこの名前を表示します。

2. [ **アカウントの追加**] をクリックし、この通話キューで使用するリソースアカウントを検索して、[ **追加**]、[ **追加**] の順にクリックします。

3. 言語を選択します。 この言語は、システムによって生成される音声プロンプトとボイスメール (有効にしている場合) に使用されます。

## <a name="greetings-and-music-on-hold-in-queue"></a>キューに入っているグリーティングと音楽

キューに到着したときに応答メッセージを再生するかどうかを指定します。 再生する応答メッセージが含まれている MP3、WAV、または WMA ファイルをアップロードする必要があります。

チームはキュー内で保留中の場合、既定の音楽を発信者に提供します。 特定のオーディオファイルを再生する場合は、[ **オーディオファイルの再生** ] を選択し、MP3、WAV、または WMA ファイルをアップロードします。

> [!NOTE]
> アップロードされたレコーディングのサイズは、5 MB 以下でなければなりません。
> Teams の通話キューに用意されている既定の音楽は、組織によって支払われる印税のうち、無料です。 

## <a name="call-agents"></a>通話エージェント

エージェントを通話キューに追加できるようにするためには、 [前提条件](plan-auto-attendant-call-queue.md#prerequisites) を参照してください。

![通話キューの [ユーザーとグループ] 設定のスクリーンショット](media/call-queue-users-groups.png)

最大20個のエージェントを個別に追加したり、グループを使用して最大で200のエージェントを追加したりできます。

キューにユーザーを追加するには、[ **ユーザーの追加**] をクリックし、ユーザーを検索して [ **追加**] をクリックし、[ **追加**] をクリックします。

キューにグループを追加するには、[ **グループの追加**] をクリックし、グループを検索して [ **追加**] をクリックし、[ **追加**] をクリックします。 配布リスト、セキュリティグループ、Microsoft 365 グループ、または Microsoft Teams teams を使用できます。

> [!NOTE]
> グループに追加された新規ユーザーは、最初の通話が到着するまでに最大8時間かかることがあります。

## <a name="call-routing"></a>通話ルーティング

![会議モードとルーティング方法の設定のスクリーンショット](media/call-queue-conference-mode-routing-method.png)

**会議モード** では、エージェントが通話を受け入れた後に、発信者がエージェントに接続するのにかかる時間が大幅に短縮されます。 会議モードで機能するには、通話キュー内のエージェントで次のいずれかのクライアントを使用する必要があります。

  - 最新バージョンの Microsoft Teams デスクトップクライアント、Android アプリ、または iOS アプリ
  - Microsoft Teams phone バージョン 1449/1.0.94.2020051601 以降
  
エージェントの Teams アカウントは、チーム専用モードに設定する必要があります。 要件を満たしていないエージェントは、通話ルーティングリストに含まれません。 すべてのエージェントが互換性のあるクライアントを使用している場合は、通話キューの会議モードを有効にすることをお勧めします。

> [!NOTE]
> Busy がビジー状態であるため、会議モードでサポートされていません。 プレゼンスベースのルーティングが有効になっていない場合は、着信キュー以外の通話に含まれているエージェントでも、通話キューの呼び出しと共に表示されることがあります。

**ルーティングメソッド** は、エージェントがキューから呼び出しを受け取る順序を決定します。 以下のオプションから選択します。

- **応答ルーティング** は、キュー内のすべてのエージェントを同時に呼び出します。 通話を受ける最初のコールエージェントは、通話を受け取ります。

- **シリアルルーティング** は **、通話エージェントリストで** 指定された順序で、すべての通話エージェントを1つずつ呼び出します。 エージェントが終了した場合、または通話を受信しなかった場合、通話は次のエージェントを呼び出し、それが処理されるかタイムアウトするまで、すべてのエージェントを試します。

- **ラウンドロビン** は、着信呼び出しのルーティングを保留して、各通話エージェントがキューから同じ回数の通話を取得できるようにします。 これは、すべての通話エージェントで同一の営業案件を確保するために、着信の販売環境で望ましい場合があります。

- [**最長アイドル** 時間 (idle) を選びます。通話は、アイドル状態になっているエージェントへの通話ごとに最も長い時間がかかる。 エージェントは、プレゼンス状態が利用可能な場合、またはプレゼンス状態が10分未満に退席中の場合に、アイドルと見なされます。 10分以上放置されているプレゼンス状態を持つエージェントは、アイドルと見なされず、通話を受信可能に変更するまで、着信を受けることはできません。 

![ルーティング、オプトイン、およびアラート時間の設定のスクリーンショット](media/call-queue-presence-agents-time.png)


**プレゼンスベースのルーティング** では、選択したルーティングメソッドの呼び出しルーティングリストにエージェントを含める必要があるかどうかを判断するために、通話エージェントの状態が使用可能になります。 連絡可能状態が [ **利用可能** ] に設定されている通話エージェントは、通話ルーティングリストに含まれており、着信を受け取ることができます。 可用性の状態が「その他」の状態に設定されているエージェントは、通話ルーティングリストから除外され、その状態が [連絡 **可能**] に戻るまでは通話を受信しません。 

任意のルーティング方法を使って、プレゼンスベースの通話ルーティングを有効にすることができます。

エージェントによって通話が発信されない場合、その状態がどのように設定されているかにかかわらず、通話ルーティングリストに含まれません。 

> [!NOTE]
> プレゼンスベースのルーティングが有効になっている場合、Skype for Business クライアントを使用するエージェントは、通話ルーティングリストに含まれません。 Skype for Business を使用するエージェントがある場合は、プレゼンスベースの通話ルーティングを有効にしないでください。

[**エージェントの通知時間**] は、エージェントの電話が次のエージェントへの呼び出しをリダイレクトするまでの、エージェントの電話が着信するまでの時間を指定します。

高ボリュームキューの場合は、次の設定をお勧めします。

- **自動****会議モード**
- **ルーティングメソッド** と **アテンダントルーティング**
- **オン** になった **プレゼンスベースのルーティング**
- **エージェントの通知時間:** **20 秒**

## <a name="call-overflow-handling"></a>通話オーバーフロー処理

![通話のオーバーフロー設定のスクリーンショット](media/call-queue-overflow-handling.png)

**キュー内の最大の通話** キューで待機できる通話の最大数を指定します。 既定値は50ですが、0 ~ 200 の範囲で指定できます。 この制限に達すると、通話 **の最大数に達したとき** にによって指定された呼び出しが処理されます。

通話を切断するか、いずれかの通話ルーティング先にリダイレクトするかを選ぶことができます。 たとえば、キュー内のエージェントのボイスメールを発信者が退出させている場合があります。 外部転送については、「 [前提条件](plan-auto-attendant-call-queue.md#prerequisites) と [外部電話番号の転送](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 」を参照してください。数値の書式設定の技術的な詳細。

> [!NOTE]
> 通話の最大数が0に設定されている場合、グリーティングメッセージは再生されません。

## <a name="call-timeout-handling"></a>通話タイムアウト処理

![通話タイムアウト設定のスクリーンショット](media/call-queue-timeout-handling.png)

**通話タイムアウト: 待ち時間** の最大値を指定すると、通話がリダイレクトされるか切断されるまでの間、キュー内で通話を保留できます。 0秒から45分までの値を指定できます。

通話を切断するか、いずれかの通話ルーティング先にリダイレクトするかを選択できます。 たとえば、キュー内のエージェントのボイスメールを発信者が退出させている場合があります。 外部転送については、「 [前提条件](plan-auto-attendant-call-queue.md#prerequisites) と [外部電話番号の転送](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 」を参照してください。数値の書式設定の技術的な詳細。

通話タイムアウトオプションを選んだら、[ **保存**] をクリックします。

## <a name="caller-id-for-outbound-calls"></a>発信通話の発信者番号

通話キュー内のエージェントは、顧客からの通話を返すためにダイヤルアウトする可能性があるため、通話キューのメンバーの発信者番号を適切な自動応答のサービス番号に設定することを検討してください。 詳細については、「 [Microsoft Teams で発信者番号通知ポリシーを管理](caller-id-policies.md) する」を参照してください。

## <a name="supported-clients"></a>サポートされるクライアント

- 通話キューのコールエージェントでは、次のクライアントがサポートされています。

  - Skype for Business デスクトップクライアント 2016 (32 ビットバージョンと64ビットバージョン)
  - Lync デスクトップクライアント 2013 (32 ビットバージョンと64ビットバージョン)
  - Microsoft Teams でサポートされているすべての IP 電話モデル。 「 [Skype For Business Online の電話を取得する」を](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)参照してください。
  - Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)
  - Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)
  - iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)
  - Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)
  - Microsoft Teams Windows クライアント (32 ビット版と64ビット版)
  - Microsoft Teams Mac クライアント
  - Microsoft Teams iPhone アプリ
  - Microsoft Teams Android アプリ

    > [!NOTE]
    > 直接ルーティング番号が割り当てられている通話キューは、Skype for Business クライアント、Lync クライアント、または Skype for Business の IP 電話をエージェントとしてサポートしません。

## <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

Windows PowerShell を使用して通話キューを作成し、設定することもできます。 通話キューを管理するために使用するコマンドレットを以下に示します。

- [新規-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>関連項目

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新しい Csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
