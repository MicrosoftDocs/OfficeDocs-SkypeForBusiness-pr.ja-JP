---
title: 呼び出しキューを作成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Microsoft Teams でクラウド通話キューの電話システムをセットアップする方法について説明します。
ms.openlocfilehash: 644b551caaf8dbc2cabc0dd5ff4b4d0199aae766
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131638"
---
# <a name="create-a-cloud-call-queue"></a>クラウドの通話キューを作成する

クラウド通話キューでは次の情報を提供できます。

- あいさつメッセージ。
- 通話の保留中に再生される保留音。
- メール対応配布リストとセキュリティ グループを使用した、コール エージェントへの通話のリダイレクト。
- キューの最大サイズ、タイムアウト、通話処理オプションなどのさまざまなパラメーターを設定します。

[リソースアカウント](manage-resource-accounts.md)を使用して、電話番号を通話キューに関連付けることができます。 通話キューには、自動応答の選択によって直接ダイヤルするか、アクセスすることができます。

発信者は、保留中の音楽を聞くことができます。通話は、*先入れ先出し*(FIFO) の順序で通話エージェントに接続します。

キュー内のすべての通話は、次のいずれかの方法でエージェントに送信されます。

- アテンダントルーティングを使用すると、キューの最初の呼び出しですべてのエージェントが同時に呼び出されます。
- シリアルルーティングでは、キューにある最初の呼び出しによって、すべてのコールエージェントが1つずつリングされます。
- ラウンドロビンでは、着信のルーティングが分散され、各通話エージェントがキューから同じ数の通話を取得できるようになります。

    > [!NOTE]
    > **オフライン**の通話エージェントは、自分のプレゼンスが [**応答不可]** に設定されています。または、通話キューを無効にしても、通話を受けることはできません。

- 一度に1つの着信通知 (キューの先頭にある通話用) のみが通話エージェントに送信されます。
- コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。

> [!NOTE]
> この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。

## <a name="step-1--get-started"></a>手順 1-はじめに

通話キューを使用する場合は、次の重要な点について留意してください。

- 通話キューには、関連するリソースアカウントが必要です。 リソースアカウントの詳細については、「[チームのリソースアカウントを管理](manage-resource-accounts.md)する」を参照してください。
- リソースアカウントに電話番号を割り当てると、無料電話システムの[仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)を使用できるようになります。 電話システムでは、低コストの自動応答と通話キューサービスを使用するために、組織レベルで電話番号を使うことができます。

> [!NOTE]
> 通話キューの直接ルーティングサービス番号は、Microsoft Teams ユーザーとエージェントに対してのみサポートされています。

> [!NOTE]
> インターネットに接続している組織内のユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズ voip に対応しているか、Office 365 の通話プランを使用している必要があります。 「 [Skype For business ライセンスの割り当て](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」または「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Office 365 の通話プランの詳細については、「[電話システムと通話プラン](calling-plan-landing-page.md)」および「 [Office 365 の通話プラン](calling-plans-for-office-365.md)」を参照してください。

- クラウド通話キューを割り当てることができるのは、 **Microsoft Teams 管理センター**で取得した、または別のサービスプロバイダーから転送された有料またはフリーダイヤルのサービス電話番号だけです。 無料サービス番号には、通信クレジットが必要です。

    > [!NOTE]
    > ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。

- クラウドの通話キューに関連付けられた通話エージェントは、次のクライアントでサポートされます。

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
    > 直接ルーティング番号が割り当てられた通話キューは、Skype for Business クライアント、Lync クライアント、または Skype for Business IP 電話をエージェントとしてサポートしません。 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>手順 2-有料またはフリーダイヤルのサービス電話番号を取得または移行する

通話キューを作成して設定する前に、既存の有料または無料のサービス番号を取得または移行する必要があります。 有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **従来のポータル** > **ボイス** > **電話番号**に表示され、**番号の種類**は以下のようになります。**サービス: フリーダイヤル**。 サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。

> [!NOTE]
> 米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。 「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」に移動して、米国以外の地域での実行方法を確認します。

複数の自動応答を設定すると、メインの自動応答のリソースアカウントに電話番号を割り当てることができます。これにより、発信者は通話キューまたはネストされた自動応答になります。 このような場合は、ダイヤルパッドオプションを割り当てずに、システムですべての自動応答と通話キューを作成し、後で設定を編集します。 このことが必要になるのは、まだ存在していない通話キューまたは自動応答にリンクするオプションを作成できないためです。

## <a name="step-3--create-a-new-call-queue"></a>手順 3-新しい通話キューを作成する

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> すべての通話キューには、[リソースアカウント](manage-resource-accounts.md)が関連付けられている必要があります。 最初にリソースアカウントを作成してから、それを通話キューに関連付けることができます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

**Microsoft Teams 管理センター**の [**音声** > **通話キュー**] で、[ **+ Add new**] をクリックします。

### <a name="set-the-call-queue-display-name-and-resource-account"></a>通話キューの表示名とリソースアカウントを設定する

![番号付き吹き出しが含まれる新しい通話キューのスクリーンショット](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![番号1のアイコン、前のスクリーンショット](media/sfbcallout1.png)
**名**で吹き出しを参照する通話キューのわかりやすい表示名を入力します。 この名前は必須であり、スペースなどの最大64文字を含めることができます。

 この名前は、着信通話の通知に表示されます。

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

**アカウントを追加**するリソースアカウントを選択します。 リソースアカウントは、通話キューの有料または無料の電話番号と関連付けられている場合と関連付けられていない場合もありますが、各通話キューには関連するリソースアカウントが必要です。

リストが表示されない場合は、前に説明したように、サービス番号を取得してリソースアカウントに割り当てておく必要があります。 サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」を参照してください。 通話キューに関連付けられた電話番号が必要な場合は、「 [Teams のリソースアカウントを管理](manage-resource-accounts.md)する」の説明に従ってリソースアカウントを作成します。

> [!NOTE]
> **ドメイン**を割り当てる必要がある場合は、それを呼び出しキューのリソースアカウントに割り当てます。

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>応答メッセージおよび保留中の保留音を設定する

![[応答メッセージ] と [音楽] オプションのスクリーンショット。番号付き吹き出し](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

**応答メッセージ**は省略可能です。 これは、通話キュー番号にコールインした相手に対して再生される応答メッセージです。

オーディオファイル (.wav、.mp3、または .wma 形式) をアップロードできます。

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

**保留中の音楽**通話キューで提供される既定の保留中の音楽を使用するか、または .wav、mp3、または .wma 形式のオーディオファイルをアップロードして、カスタム音楽を保留にすることができます。

* * *

### <a name="select-the-call-answering-options"></a>通話応答のオプションを選択する

![番号付き吹き出しが含まれる通話応答オプションのスクリーンショット](media/5d249515-d532-4af2-90da-011404028b89.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

以下のメーリングリストまたはグループのいずれかに属する、最大200の通話エージェントを選択できます。

- Office 365 グループ
- セキュリティグループ
- 配布リスト

選択されているコールエージェントは、次のいずれかである必要があります。 

- 電話システムのライセンスを持つオンラインユーザーとエンタープライズ Voip が有効になっている 
- 通話プランを使用するオンラインユーザー
- オンプレミスの Skype for Business Server ユーザー

  > [!NOTE]
  > これは、オンラインの組織内のユーザーに通話をリダイレクトする場合にも該当します。 これらの個人は、**電話システム**のライセンスとエンタープライズボイスを有効にしている**か**、通話プランを利用している必要があります。 詳細については、「 [Skype For business ライセンスの割り当て](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、 [Microsoft Teams ライセンスの割り当て](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)、または[適切な通話プラン](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)」を参照してください。

 エンタープライズ Voip のエージェントを有効にするには、Windows PowerShell を使用します。 たとえば、次を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- **電話システム**のライセンスを持っているか、Office 365 グループに追加された通話プランを持っているユーザーメールが有効な配布リストまたはセキュリティグループ。 配布リストまたはセキュリティグループに新しく追加されたエージェントが、通話キューからの着信の受信を開始するまでに最大3時間かかることがあります。 新しく作成した分配リストまたはセキュリティ グループでは、通話キューで使用可能になるまで最大で48時間を要する場合があります。 新しく作成された Office 365 グループは、ほぼ瞬時にご利用可能です。

- 担当者が Microsoft Teams アプリを使って通話キューの呼び出しを実行している場合は、チームメンバーが Teams Sonly モードである必要があります。

![[コールエージェントの追加] ウィンドウのスクリーンショット](media/skype-for-business-add-agents-to-call-queue.png)

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

**ルーティング方法**通話キューの配布方法には、**アテンダント**、**シリアル**、または**ラウンドロビン**のいずれかを選ぶことができます。 新規および既存のすべての通話キューは、応答のルーティングが既定値で選択されます。 アテンダントルーティングを使うと、キューの最初の呼び出しによって、すべてのコールエージェントが同時に呼び出されます。 通話を受ける最初のコールエージェントは、通話を受け取ります。

- **アテンダントルーティング**を行うと、キュー内の最初の呼び出しがすべてのコールエージェントを同時に呼び出します。 通話を受ける最初のコールエージェントは、通話を受け取ります。
- **シリアルルーティング**着信エージェントの一覧の先頭から1つずつ呼び出しエージェントが呼び出されます。 通話エージェントの一覧内では、エージェントを注文することはできません。 エージェントが退出中、または応答しない場合、リスト上の次のエージェントを呼び出し、キューで待機中の発信が応答するかタイムアウトになるまで、すべてのエージェントの呼び出しを 1 件ずつ試みます。
  > [!NOTE]
  > **オフライン**中、**取り込み中**表示、またはこのキューからの着信を **オプトアウト** したエージェントは、シリアルルーティングからスキップされます。
- **ラウンドロビン**は、着信呼び出しのルーティングを分散し、各呼び出しエージェントがキューから同じ数の通話を取得できるようにします。 これは、すべての通話エージェントで同一の営業案件を確保するために、着信の販売環境で望ましい場合があります。

### <a name="select-an-agent-opt-out-option"></a>エージェントのオプトアウトオプションを選択する

![番号付き吹き出しが含まれる、エージェントのオプトアウトオプションのスクリーンショット](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

**エージェントが通話を受けることができ**ないこのオプションを有効にすると、通話キューエージェントが特定のキューからの呼び出しを行わないようにすることができます。

このオプションを有効にすると、このキュー内のすべてのエージェントは、この通話キューからの着信の受信を開始または停止することができます。 チェックボックスの削除することによっていつでもオプトアウトの取消しが可能で、オプトアウトされたエージェントはこの通話キューへ自動的にもう一度オプトインされます。 (すべてのエージェントの初期設定)

エージェントは次の操作を行うと、オプトアウトのオプションにアクセスできます:

 1. Skype for Business クライアントデスクトップで、 **オプション** を開きます。
 2. **[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。
 3. [ユーザー設定] ページで、[**通話キュー**] をクリックし、脱退するキューのチェックボックスをオフにします。

    > [!NOTE]
    > Skype for Business デスクトップ以外のアプリまたはエンドポイントを使用するエージェントは、ユーザー設定ポータル[https://aka.ms/cqsettings](https://aka.ms/cqsettings)から脱退オプションにアクセスできます。

![前のスクリーンショット](media/sfbcallout2.png)
の**通知設定**で吹き出しを参照している番号2のアイコン

これは、シリアルまたはラウンドロビンルーティングメソッドが次のエージェントに移動する前に、通話の通知を受けるエージェントの期間を定義します。

既定の設定は30秒ですが、最大3分に設定することができます。

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>通話のオーバーフローとタイムアウト処理のオプションを設定する

![番号付き吹き出しが含まれるオーバーフロー処理オプションのスクリーンショット](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。 既定値は50ですが、0 ~ 200 の範囲で指定できます。 この制限に達すると、通話は以下の [**通話の最大数に達した場合**] 設定で設定した方法で処理されます。

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

**通話の最大数に達した場合**通話キューが最大サイズ (**キュー設定の最大の通話**を使用して設定) に達すると、新しい着信呼び出しに何が起こるかを選ぶことができます。

- **切断**通話が切断されます。
- **リダイレクト先**選択する場合は、次のいずれかを選択します。

  - **社内のユーザー** **電話システム** のライセンスを持つオンラインのユーザーそしてエンタープライズ ボイス を有効にするか通話プランを取得する必要があります。 発信者がボイスメールに送信できるように設定できます。 これを行うには、**社内のユーザ**を選択して、そのユーザが直接ボイスメールに転送するように設定します。

  ボイスメールに必要なライセンスについては、「[クラウドボイスメールのセットアップ](set-up-phone-system-voicemail.md)」をご覧ください。

  - **音声アプリケーション**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。

* * *

![前のスクリーンショットで吹き出しを参照している数値3のアイコン](media/sfbcallout3.png)

**通話タイムアウト: 最大待機時間**また、通話がタイムアウトとなり、リダイレクトまたは切断する必要があるときに、通話を保留する時間を決定することもできます。 リダイレクトされる場所は、**通話**のタイムアウト設定を設定する方法に基づいています。 0 から 45 分に設定できます。

タイムアウト値は秒単位で、 15 秒間隔で設定することができます。 これにより、通話フローを細かく操作することができます。 たとえば、エージェントによって応答されないすべての通話を30秒以内に指定して、ディレクトリ検索の自動応答に移動することができます。

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

**通話がタイムアウトになったとき**通話が [キュー] 設定で、通話の**待ち時間**として設定した限度額に達した場合は、この通話に対する処理を選択できます。

- **切断**通話が切断されます。
- **この通話のリダイレクト先**このオプションを選択すると、次のオプションが表示されます。
  - **社内のユーザー** **電話システム** のライセンスを持つオンラインユーザーで、エンタープライズ ボイス が有効化されているまたは、通話プランを取得済みである必要があります。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うには、**社内のユーザ**を選択して、そのユーザが直接ボイスメールに転送するように設定します。

  ボイスメールに必要なライセンスについては、「[クラウドボイスメール](set-up-phone-system-voicemail.md)をセットアップする」をご覧ください。

  - **音声アプリケーション**既に作成されている通話キューまたは自動応答のいずれかに関連付けられているリソースアカウントの名前を選択します。

## <a name="change-a-users-caller-id-for-outbound-calls"></a>発信通話のユーザーの発信者番号認識を変更する

ユーザーの id を保護するには、 **CsCallingLineIdentity**コマンドレットを使用する代わりに、通話キュー、自動応答、または任意のサービス番号への発信通話の発信者番号を変更します。

これを行う場合は、次を実行します。

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

**Grant-CallingLineIdentity** コマンドレットを使用してユーザーのポリシーを適用します。 これを行う場合は、次を実行します。

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

組織で発信者番号の設定を行う方法については、「[組織での発信者番号の使用方法](/microsoftteams/how-can-caller-id-be-used-in-your-organization)」を参照してください。

## <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

Windows PowerShell を使用して通話キューを作成し、設定することもできます。 通話キューを管理するために使用するコマンドレットを以下に示します。

- [新規-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細について

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Office 365 および Microsoft Teams を管理し、日常的な作業を簡略化することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Office 365 PowerShell を使用する必要がある理由](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell には、多くのユーザーに対して同時に設定を変更する場合など、Microsoft Teams 管理センターでの速度、シンプルさ、生産性を高めるためのさまざまな利点があります。 次のトピックでこれらの利点について説明します。

  - [Windows PowerShell を使用して Office 365 を管理する](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Windows PowerShell 用にコンピューターをセットアップする](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>関連トピック

[Office 365 の電話システムでできること](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新しい Csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
