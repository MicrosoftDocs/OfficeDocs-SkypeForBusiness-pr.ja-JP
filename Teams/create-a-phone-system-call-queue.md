---
title: 呼び出しキューを作成する
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: このページでは、Microsoft Teams で電話システムをセットアップする方法について説明します。これにより、あいさつメッセージの送信、音楽の保留、リダイレクト、その他の機能を行うことができます。
ms.openlocfilehash: ac0fb41ebb85a6e7e80d3d221da4dabf456d20aa
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44697412"
---
# <a name="create-a-cloud-call-queue"></a>クラウドの通話キューを作成する

クラウド通話キューでは次の情報を提供できます。

- あいさつメッセージ。
- 通話の保留中に再生される保留音。
- メール対応配布リストとセキュリティ グループを使用した、コール エージェントへの通話のリダイレクト。
- キューの最大サイズ、タイムアウト、通話処理オプションなどのさまざまなパラメーターを設定します。
- 発信者が組織のメッセージを残すための共有ボイスメール。

電話番号を通話キューに直接関連付けないでください。電話番号は[リソースアカウント](manage-resource-accounts.md)に関連付けられています。 通話キューには、自動応答の選択によって直接ダイヤルするか、アクセスすることができます。

発信者は、保留中の音楽を聞くことができます。通話は、*先入れ先出し*(FIFO) の順序で通話エージェントに接続します。

キュー内のすべての通話は、次のいずれかの方法でエージェントに送信されます。

- アテンダントルーティングを使用すると、キューの最初の呼び出しですべてのエージェントが同時に呼び出されます。
- シリアルルーティングでは、キューにある最初の呼び出しによって、すべてのコールエージェントが1つずつリングされます。
- アイドル状態のルーティングが最長でアイドル状態になると、アイドル状態になった通話エージェントは、次に使用可能な通話を受け取ります。 アイドル時間は、通話のときに、通話エージェントのプレゼンス状態が [**利用可能**] または [**退席**中] (10 分未満) に設定されている時間の長さとして定義されます。 通話エージェントのプレゼンスが10分以上**退席**中の場合は、アイドルタイマーがリセットされます。
- ラウンドロビンでは、着信のルーティングが分散され、各通話エージェントがキューから同じ数の通話を取得できるようになります。

上のいずれかの方法を使用して、エージェントのオプトイン/オプトアウト、プレゼンスベースのルーティング、通話待ち時間、通話タイムアウトオプションなどの通話処理オプションを設定できます。

一度に1つの着信通知 (キューの先頭にある通話用) のみが通話エージェントに送信されます。 コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。

> [!NOTE]
> この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。

## <a name="step-1--get-started"></a>手順 1-はじめに

通話キューを使用する場合は、次の重要な点について留意してください。

- 通話キューには、関連するリソースアカウントが必要です。 リソースアカウントの詳細については、「[チームのリソースアカウントを管理](manage-resource-accounts.md)する」を参照してください。
- リソースアカウントに電話番号を割り当てると、無料電話システムの[仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)を使用できるようになります。 電話システムでは、低コストの自動応答と通話キューサービスを使用するために、組織レベルで電話番号を使うことができます。

  > [!NOTE]
  > 通話キューの直接ルーティングサービス番号は、Microsoft Teams ユーザーとエージェントに対してのみサポートされています。

> [!NOTE]
> インターネットに接続している組織内のユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズボイスに対して有効になっているか、Microsoft 365 または Office 365 の通話プランを使用している必要があります。 「 [Microsoft Teams のアドオンライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)」を参照してください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- 通話プランの詳細については、「[電話システムと通話プラン](calling-plan-landing-page.md)」および「 [Microsoft 365 または Office 365 の通話](calling-plans-for-office-365.md)プラン」を参照してください。

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
    > 直接ルーティング番号が割り当てられている通話キューは、Skype for Business クライアント、Lync クライアント、または Skype for Business の IP 電話をエージェントとしてサポートしません。

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a>手順 2-有料または無料のサービス電話番号を取得または移行する

通話キューを作成して設定する前に、既存の有料または無料のサービス番号を取得または移行する必要があります。 サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「[チームに電話番号を移行](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)する」をご覧ください。 有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター**の  >  **ボイス**  >  **電話番号**に表示されます。 無料電話番号には、無料の電話**番号**が付い**ています**。

> [!NOTE]
> 米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。 「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」に移動して、米国以外の地域での実行方法を確認します。

複数の自動応答を設定する場合、通常は、メインの自動応答のリソースアカウントに電話番号を割り当てます。 入れ子になった自動応答または通話キューに関連付けられているリソースアカウントには、電話番号は必要ありません。 この自動応答では、電話番号がない場合でも、通話キューまたはネストされた自動応答に発信者を誘導することができます。 このような場合は、ダイヤルパッドオプションを割り当てずに、システムですべての自動応答と通話キューを作成し、後で設定を編集することができます。 メニューオプションとして設定するには、通話キューまたは自動応答が存在している必要があります。

## <a name="step-3--create-a-call-queue"></a>手順3—通話キューを作成する

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> すべての通話キューには、[リソースアカウント](manage-resource-accounts.md)が関連付けられている必要があります。 最初にリソースアカウントを作成してから、それを通話キューに関連付けることができます。

### <a name="use-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用する

**Microsoft Teams 管理センター**の [**音声**  >  **通話キュー**] で、[ **+ Add new**] をクリックします。

### <a name="set-the-display-name-and-resource-account"></a>表示名とリソースアカウントを設定する

![番号付き吹き出しが含まれる新しい通話キューのスクリーンショット](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![数字1のアイコン: 前のスクリーンショット名の吹き出しを参照し ](media/teamscallout1.png)
 **Name**ます。通話キューのわかりやすい表示名を入力します。 この名前は必須であり、スペースなどの最大64文字を含めることができます。

 この名前は、着信通話の通知に表示されます。

* * *

![数字2のアイコン: 前のスクリーンショットで吹き出しを参照している ](media/teamscallout2.png)
 **アカウントを追加**するリソースアカウントを選択します。 すべての通話キューには、リソースアカウントが必要です。 リソースアカウントには、有料または無料の電話番号が必要です。

リストが表示されない場合は、前に説明したように、通話キューを作成する前に、サービス番号を取得してリソースアカウントに割り当てます。 サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」を参照してください。 電話番号の割り当て方法の詳細については、「 [Teams のリソースアカウントを管理](manage-resource-accounts.md)する」を参照してください。

> [!NOTE]
> 必要に応じて、またはドメインを割り当てる必要がある場合は、その**ドメイン**を通話キューのリソースアカウントに割り当てます。

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>応答メッセージおよび保留中の保留音を設定する

![[応答メッセージ] と [音楽] オプションのスクリーンショット。番号付き吹き出し](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![数字1のアイコン: 前のスクリーンショットの吹き出しを参照して ](media/teamscallout1.png)
 います通話キューの番号を呼び出すユーザーに対して、オプションの応答**メッセージを**表示します。

オーディオファイル (.wav、.mp3、または .wma 形式) をアップロードできます。

![数字2のアイコン: 前のスクリーンショットの音楽の中で吹き出しを参照 ](media/teamscallout2.png)
 **Music on hold**する通話キューで提供される既定の音楽を保留にすることができます。 .Wav、mp3、または .wma 形式のオーディオファイルをアップロードして、カスタム音楽として保留にすることもできます。

* * *

### <a name="select-the-call-answering-options"></a>通話応答のオプションを選択する

![通話応答オプションのスクリーンショット](media/teams-cq-call-answering-options.png)

![数字1のアイコン: 前のスクリーンショットの ](media/teamscallout1.png)
 **コールエージェントとグループ**の吹き出しを参照して、個々のエージェントをグループに追加してから、[**ユーザーの追加**] をクリックします。 通話を受ける順序に個々のエージェントを追加します。 最大20の個別のエージェントを追加できます (20 を超える場合は、1つのグループにまとめることができます)。

通話は最初に個々のエージェントにルーティングされ、その後、グループ内のエージェントに送信されます。 

以下のメーリングリストまたはグループのいずれかに属する、最大200の通話エージェントを選択できます。

- Microsoft 365 グループ
- セキュリティグループ
- 配布リスト

選択されているコールエージェントは、次のいずれかである必要があります。 

- 電話システムのライセンスを持つオンラインユーザーとエンタープライズ Voip が有効になっている
- 通話プランを使用するオンラインユーザー
- オンプレミスの Skype for Business Server ユーザー

  > [!NOTE]
  > これは、オンラインの組織内のユーザーに通話をリダイレクトする場合にも該当します。 これらの個人は、**電話システム**のライセンスとエンタープライズボイスを有効にしている*か*、通話プランを利用している必要があります。 詳細については、「 [Skype For business ライセンスの割り当て](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)、 [Microsoft Teams ライセンスの割り当て](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)、または[適切な通話プラン](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)」を参照してください。

   エンタープライズ Voip のエージェントを有効にするには、Windows PowerShell を使用します。 たとえば、次を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- **電話システム**のライセンスを持っているか、Microsoft 365 グループ、メールが有効な配布リスト、またはセキュリティグループに追加された通話プランを持っているユーザー。 配布リストまたはセキュリティグループのエージェントを呼び出しキューエージェントとして追加する場合、最初の呼び出しが到着するまでに最大3時間かかることがあります。 新しく作成した分配リストまたはセキュリティ グループでは、通話キューで使用可能になるまで最大で48時間を要する場合があります。 新しく作成された Microsoft 365 グループは、ほぼ瞬時に利用できます。

- 使用しているエージェントで、Microsoft Teams アプリを呼び出しキューとして使用している場合は、そのモードである必要があります。

![数字2のアイコン: 前のスクリーンショットで吹き出しを参照し ](media/teamscallout2.png)
 ます。**会議モード**の会議モードでは、エージェントが通話を受け入れた後に、発信者がエージェントに接続するのにかかる時間が大幅に短縮されます。 複数の通話キューがある場合は、一部またはすべての通話キューで会議モードを有効にすることができます。1つの通話キューで会議モードを有効または無効にしても、他の通話キューに影響はありません。

会議モードは既定で無効になっていますが、次の要件が満たされている場合はいつでも有効にすることができます。

- 通話キューに追加されたエージェントは、次のいずれかのクライアントを使用する必要があります。
  - 最新バージョンの Microsoft Teams デスクトップクライアント、Android アプリ、または iOS アプリ
  - Microsoft Teams phone バージョン 1449/1.0.94.2020051601 以降
- エージェントの Teams アカウントをチーム専用モードに設定する必要がある

> [!IMPORTANT]
> 上記のエージェント要件が満たされておらず、通話キューで会議モードが有効になっている場合、要件を満たしていないエージェントは通話ルーティングリストに含まれません。 通話ルーティングリストに含まれていないエージェントは、通話を受信できません。 上記のエージェント要件を満たしていないエージェントがある場合は、通話キューで会議モードを有効にしないようにします。

通話キューで電話会議モードが有効になると、次のいずれかの方法で通話を受信すると、接続時間が短縮されます。

- 他の Microsoft Teams デスクトップクライアントからの VoIP 通話
- 通話プラン PSTN 通話
- PSTN 通話のダイレクトルーティング

通話の大半は、上記のいずれかの方法で受信します。 別の方法 (Skype for Business クライアントからの VoIP 通話など) 経由で通話を受信した場合でも、通話は通話キューに追加されますが、接続時間が短縮されることはありません。

![数値3のアイコンは、前のスクリーンショットルーティングメソッドで吹き出しを参照し ](media/teamscallout3.png)
 **Routing method**ています。これは、配布方法として、**アテンダント**、**シリアル**、**アイドル**、または**ラウンドロビン**のいずれかを選ぶことができます。 すべての新規および既存の通話キューには、既定で [アテンダントルーティング] が選択されています。 アテンダントルーティングを使うと、キューの最初の呼び出しによって、すべてのコールエージェントが同時に呼び出されます。 通話を受ける最初のコールエージェントは、通話を受け取ります。

- **アテンダントルーティング**を行うと、キュー内の最初の呼び出しがすべてのコールエージェントを同時に呼び出します。 通話を受ける最初のコールエージェントは、通話を受け取ります。
- **シリアルルーティング**着信エージェントリストの先頭から、すべての通話エージェントを1つずつ呼び出します。 通話エージェントの一覧内では、エージェントを注文することはできません。 エージェントが終了した場合、または通話を受信しなかった場合、通話は次のエージェントを呼び出し、それが処理されるかタイムアウトするまで、すべてのエージェントを試します。
- [**最長アイドル**] は、アイドル状態になっている通話エージェントへの次の使用可能な通話をルーティングします。 アイドル時間は、通話のときに、通話エージェントのプレゼンス状態が [**利用可能**] または [**退席**中] (10 分未満) に設定されている時間の長さとして定義されます。 10分以上経過すると、通話エージェントのプレゼンスが [**退席**中] に設定されていると、アイドルタイマーがリセットされます。 ユーザーのプレゼンス状態は、1分ごとに照会されます。

    この設定を有効にすると、**プレゼンスベースのルーティング**も有効になることを知っておくことが重要です。

    > [!IMPORTANT]
    > Skype for Business クライアントを使用するエージェントは、最長アイドル設定が有効になっていると、通話を受信できません。 担当者が Skype または Business を使用している場合は、この設定を有効にしないでください。
- **ラウンドロビン**は、着信呼び出しのルーティングを分散し、各呼び出しエージェントがキューから同じ数の通話を取得できるようにします。 これは、すべての通話エージェントで同一の営業案件を確保するために、着信の販売環境で望ましい場合があります。

![数字4のアイコン: 前のスクリーンショットのプレゼンスに基づくルーティングのプレゼンスに基づくルーティングのプレゼンスを使って、 ](media/teamscallout4.png)
 **Presence-based routing**選択したルーティングメソッドの呼び出しルーティングリストにエージェントを含める必要があるかどうかを特定します。 連絡可能状態が [**利用可能**] に設定されている通話エージェントは、通話ルーティングリストに含まれており、着信を受け取ることができます。 可用性の状態が「その他」の状態に設定されているエージェントは、通話ルーティングリストから除外され、その状態が [連絡**可能**] に戻るまでは通話を受信しません。  

任意のルーティング方法を使って、プレゼンスベースの通話ルーティングを有効にすることができます。

エージェントによって通話が発信されない場合、その状態がどのように設定されているかにかかわらず、通話ルーティングリストに含まれません。 

> [!IMPORTANT]
> Skype for Business クライアントを使用するエージェントは、可用性の状態に関係なく、プレゼンスベースのルーティングが有効になっている場合、通話ルーティングリストに含まれません。 通話ルーティングリストに含まれていないエージェントは、通話を受信できません。 Skype for Business を使用するエージェントがある場合は、プレゼンスベースの通話ルーティングを有効にしないでください。

### <a name="select-an-agent-opt-out-option"></a>エージェントのオプトアウトオプションを選択する

![番号付き吹き出しが含まれる、エージェントのオプトアウトオプションのスクリーンショット](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![番号1のアイコン、前のスクリーンショットエージェントの吹き出しを参照している場合は、このオプションを有効にすることで、特定のキューからの呼び出しを許可しないようにすることができ ](media/teamscallout1.png)
 **Agent can opt out of getting calls**ます。

このオプションを有効にすると、このキュー内のすべてのエージェントは、この通話キューからの着信の受信を開始または停止することができます。 チェックボックスの削除することによっていつでもオプトアウトの取消しが可能で、オプトアウトされたエージェントはこの通話キューへ自動的にもう一度オプトインされます。 (すべてのエージェントの初期設定)

脱退オプションにアクセスするには、次の操作を行います。

 1. Skype for Business クライアントデスクトップで、 **オプション** を開きます。
 2. **[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。
 3. [ユーザー設定] ページで、[**通話キュー**] をクリックし、[キューの停止] チェックボックスをオフにします。

    > [!NOTE]
    > Skype for Business デスクトップ以外のアプリまたはエンドポイントを使用するエージェントは、ユーザー設定ポータルから脱退オプションにアクセスでき [https://aka.ms/cqsettings](https://aka.ms/cqsettings) ます。
    >
    > エージェントが Microsoft Teams のデスクトップクライアントにある場合は、通話設定を使用してそのエージェントを除外することができます。 

![数字2のアイコン: 前のスクリーンショットの ](media/teamscallout2.png)
 **通知設定**で吹き出しを参照します。

これは、シリアルまたはラウンドロビンルーティングメソッドが次のエージェントに移動する前に、通話の通知を受けるエージェントの期間を定義します。

既定の設定は30秒ですが、最大3分に設定することができます。

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>通話のオーバーフローとタイムアウト処理のオプションを設定する

![番号付き吹き出しが含まれるオーバーフロー処理オプションのスクリーンショット](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![数値1のアイコン: 前のスクリーンショットで吹き出しを参照します ](media/teamscallout1.png)
 。**キュー内の最大の呼び出し**は、同時にキュー内で待機できる最大呼び出しを設定するために使用されます。 既定値は50ですが、0 ~ 200 の範囲で指定できます。 この制限に達すると、通話は以下の [**通話の最大数に達した場合**] 設定で設定した方法で処理されます。

* * *

![番号2のアイコンは、 ](media/teamscallout2.png)
 通話キューが最大サイズ (キュー設定の**最大呼び出し**を使用して設定されている場合) で**の通話の最大数に達し**たときに、前のスクリーンショットの吹き出しを参照しているため、新しい着信呼び出しに何が起こるかを選ぶことができます。

- **切断**通話が切断されます。
- **リダイレクト先**選択する場合は、次のいずれかを選択します。

  - **組織内のユーザー****電話システム**のライセンスを持ち、エンタープライズ voip を有効にする、または通話プランがあるオンラインユーザー。 発信者がボイスメールに送信できるように設定できます。 これを行うには、組織内のユーザーを選択して、このユーザーが直接ボイスメールに転送するように設定します。

  ボイスメールに必要なライセンスについては、「[クラウドボイスメールのセットアップ](set-up-phone-system-voicemail.md)」をご覧ください。

  - **音声アプリ**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。

* * *

![数値3のアイコンは、前のスクリーンショットで吹き出しを参照してい ](media/teamscallout3.png)
 **ます。通話タイムアウト: 最長待機時間**は、通話がタイムアウトになり、リダイレクトまたは切断する必要がある時間を決定することもできます。 リダイレクトされる場所は、**通話**のタイムアウト設定を設定する方法に基づいています。 0 から 45 分に設定できます。

タイムアウト値は秒単位で、 15 秒間隔で設定することができます。 これにより、通話フローを細かく操作することができます。 たとえば、エージェントによって応答されないすべての通話を30秒以内に指定して、ディレクトリ検索の自動応答に移動することができます。

![数字4のアイコンは、通話がキュー設定での通話の待機時間に設定した制限値に達したときに、前のスクリーンショットの吹き出しを参照している ](media/teamscallout4.png)
 **When call times out**ため、通話に対する処理を選択できます。 **How long a call can wait in the queue**

- **切断**通話が切断されます。
- **この通話のリダイレクト先**このオプションを選択すると、次のオプションが表示されます。
  - **組織内のユーザー****電話システム**のライセンスを持ち、エンタープライズ voip を有効にする、または通話プランが必要なオンラインユーザー。 通話相手がボイスメールに送信されるように設定するには、組織内のユーザを選択して、このユーザが直接ボイスメールに転送するように設定します。

  ボイスメールに必要なライセンスについては、「[クラウドボイスメールのセットアップ](set-up-phone-system-voicemail.md)」をご覧ください。

  - **音声アプリ**既に作成した通話キューまたは自動応答のいずれかに関連付けられているリソースアカウントの名前を選択します。

## <a name="change-caller-id-for-outbound-calls"></a>発信通話の発信者番号認識を変更する

通話エージェントの id を保護するには、次の例のように、 **CsCallingLineIdentity**コマンドレットを使用して、発信通話の発信者番号を、通話キュー、自動応答、または任意のサービス番号に変更します。

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

次の例のように、 **、callinglineidentity**コマンドレットを使用してユーザーにポリシーを適用します。 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

詳細については、「[組織での発信者番号の使用方法](/microsoftteams/how-can-caller-id-be-used-in-your-organization)」を参照してください。

## <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

Windows PowerShell を使用して通話キューを作成し、設定することもできます。 通話キューを管理するために使用するコマンドレットを以下に示します。

- [新規-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細について

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、1つの管理ポイントで Microsoft 365 または Office 365 および Microsoft Teams を管理することができます。 複数のタスクがある場合は、日常業務を簡素化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Office 365 PowerShell を使用する必要がある理由](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- 複数のユーザーに対して同時に変更を加える場合、Windows PowerShell では、Microsoft Teams 管理センターでの速度、シンプルさ、生産性の向上について多くの利点があります。 次のトピックでこれらの利点について説明します。

  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Windows PowerShell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>関連項目

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新しい Csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
