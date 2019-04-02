---
title: 呼び出しキューを作成します。
ms.author: jambirk
author: jambirk
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 電話システム呼び出しキューを使用すれば、組織、保留中の音楽の挨拶と配布リストおよびセキュリティ グループ内のエージェントを呼び出しへの呼び出しをリダイレクトするための電話システムを設定する方法について説明します。 You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: be8055dfe1d92caa7e3416740856ab2b6578e799
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026230"
---
# <a name="create-a-phone-system-call-queue"></a>電話システムの呼び出しキューを作成する

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
電話システムの通話キューは次の機能を提供します:
  
- 組織の応答メッセージ。
- 通話の保留中に再生される保留音。
- メールが有効な配布リストおよびセキュリティ グループ内のエージェントを呼び出しへの呼び出しをリダイレクトします。
- 呼び出しキューの最大サイズ、タイムアウト、および呼び出しの処理オプションの設定を行っています。

あいさつのメッセージを聞くを呼び出し、[リソース アカウント](manage-resource-accounts.md)を使用してキューに関連付けられている電話番号呼び出し、(いずれかの設定されている) 場合、その後に、キューを保存して、次の呼び出しを使用可能なエージェントを待機します。 待機中、保留中であるし、呼び出し*最初に、先入れ先出し*(FIFO) の順序で呼び出しエージェントに提供するときに、相手呼び出しは音楽を聞きます。
  
キューで待機しているすべての呼び出しは、次の方法のいずれかを使用して配布されます。
  
- 応答のルーティングでは、キュー内の最初の呼び出しを同時にすべてのエージェントが呼び出されます。
- シリアル・ルーティングでは、キュー内の最初の呼び出しがすべてのコールエージェントを一件ずつ呼び出します。
- ラウンド ・ ロビン、着信通話のルーティングのバランスがとれて各担当者は、キューから同じ呼び出しの数を取得できるようにします。

    > [!NOTE]
    > **オフライン**中のコールエージェントは、 **取り込み中** のプレゼンスを設定するか、通話キューからの呼び出しをオプトアウトしてください。
  
- 一度に 1 回のみの着信通知 (キューの最初にある通話) がコール エージェントに送信されます。
- コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。

> [!NOTE]
> この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。

## <a name="step-1---get-started"></a>手順 1 - 開始します。

通話キューを使用する場合は、次の重要な点について留意してください。
  
- 自動応答は、関連付けられているリソース アカウントを持っている必要があります。 リソース アカウントの詳細については、[チーム内のリソース アカウントの管理](manage-resource-accounts.md)を参照してください。
- 取得し、リソース アカウントに次のライセンスを割り当てる必要があります直接ルーティング番号を割り当てる場合は、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを\)。
- 取得し、リソース アカウントに次のライセンスを割り当てる必要がある場合は代わりに、マイクロソフトのサービス番号を割り当てることは、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを呼び出す計画と\)。

> [!NOTE] 
> マイクロソフトは、ユーザー数ライセンス モデルを使用する必要がありますのクラウドの自動応答、通話キューなどのアプリケーションの適切なライセンス ・ モデルの中です。

> [!NOTE]
> オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。 [ビジネス ライセンスの割り当ての Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)または[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次を実行します。
  
- Office 365 のプランを呼び出す方法の詳細については、[電話システムを呼び出すことを計画](calling-plan-landing-page.md)し、 [Office 365 のプランを呼び出す](calling-plans-for-office-365.md)を参照してください。

- 有料電話番号と**マイクロソフトのチーム管理センター**でまたは別のサービス プロバイダーからの呼び出しの電話システムのキューに転送する電話番号をフリー ダイヤル サービスをのみ割り当てることができます。 取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。

    > [!NOTE]
    > ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。
  
- 電話システム呼び出しキューからの着信呼び出しを配布するときは、コール エージェントのこれらのクライアントがサポートされます。

  - Skype for Business デスクトップ クライアント 2016 (32 および 64 ビット バージョン)

  - Lync デスクトップ クライアント 2013 (32 および 64 ビット バージョン)

  - マイクロソフトのチームでサポートされているすべての IP 電話モデル。 [ビジネス オンラインの Skype の電話を取得](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)を参照してください。

  - Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)

  - Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)

  - iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)

  - Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)

  - Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)

  - Microsoft Teams Mac クライアント

  - マイクロソフト チームの iPhone アプリ

  - マイクロソフト チーム Android アプリ

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>ステップ 2 - 有料またはフリーダイヤルのサービス電話番号の取得または移行

通話キューを作成し設定する前に、既存の有料または無料のサービス番号を取得もしくは転送する必要があります。 有料または無料のサービスの電話番号を取得した後表示されます**マイクロソフトのチーム管理センター**の > **音声** > **の電話番号**、および記述されている**数値型**は、**サービスのフリー ダイヤル**として一覧表示されます。 サービス番号を取得するには、[取得サービスの電話番号](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照するか、既存のサービス番号に転送する場合は、 [Office 365 に転送電話の番号](transfer-phone-numbers-to-office-365.md)を参照してください。
  
> [!NOTE]
> 米国以外のユーザーは、サービス番号を取得するマイクロソフトのチームの管理センターを使うことはできません。 [組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。

設定する場合も自動応答をメインの自動アテンダントのリソースのアカウントに電話番号を割り当てると、直接の呼び出し元、呼び出しキューに必要がありますだけです。 この場合は、呼び出しキュー呼び出しキューを選択する自動応答のオプションを作成する前に作成する必要があります。
  
## <a name="step-3---create-a-new-call-queue"></a>手順 3 - 新しい呼び出しキューを作成します。

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> 呼び出しのすべてのキューは、関連付けられている[リソースのアカウント](manage-resource-accounts.md)を持っている必要があります。 最初に、リソース アカウントを作成する必要がありますし、呼び出しのキューに関連付けることができます。

### <a name="using-the-microsoft-teams-admin-center"></a>マイクロソフトのチーム管理センターを使用してください。

で**マイクロソフトのチーム管理センター**、**音声** >  **キューを呼び出す**には、 **+ 新規追加**] をクリックします。

### <a name="set-the-call-queue-display-name-and-resource-account"></a>呼び出しキューの表示名とリソース アカウントを設定します。

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![1](media/sfbcallout1.png)
**名**呼び出しキューの説明的な表示名を入力します。 この項目は必須で、空白を含む最大 64 文字を含めることができます。

 この名前は着信の通知に表示されます。

* * *

![ナンバー 2](media/sfbcallout2.png)

**アカウントを追加します。** リソース アカウントを選択します。 リソース アカウントは、有料のサービスや、呼び出しキューの無料電話番号に関連付けられていない場合がありますが、各呼び出しキューに関連付けられているリソース アカウントが必要です。

いずれかを使用する必要がある場合は、一覧に表示する必要がありますサービスの番号を取得し、割り当てるリソース アカウントに、この呼び出しキューを作成する前に前述のとおりです。 サービス番号を取得するには、[サービスの電話番号の取得](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照してください。 に従って[チームにリソース アカウントを管理](manage-resource-accounts.md)する場合は、呼び出しのキューに関連付けられている電話番号は、リソース アカウントを作成する必要があります。

> [!NOTE]
> **ドメイン**を割り当てる必要のある場合で行う呼び出しキューのリソース アカウントに割り当てるとします。

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>応答メッセージおよび保留中の保留音を設定する

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![1](media/sfbcallout1.png)

**応答メッセージ**は省略可能です。 これは、応答メッセージが、キューの番号に電話通話する相手を再生します。

オーディオ ファイル (.wav、.mp3、.wma 形式) をアップロードすることができます。

![ナンバー 2](media/sfbcallout2.png)

**上の音楽を保持**呼び出しキューで提供されている保留中のデフォルトの音楽を使用するか、または保留中のカスタムの音楽として使用する .wav、mp3、または .wma ファイルの形式でのオーディオ ファイルをアップロードすることができます。

* * *

### <a name="select-the-call-answering-options"></a>呼び出しへの応答のオプションを選択します。

![着信分配メソッドのオプションを表示する](media/5d249515-d532-4af2-90da-011404028b89.png)

![1](media/sfbcallout1.png)

指定されたメーリング リストまたはグループに属する 200 人までのコール エージェントを選択します。 コール エージェントは、いずれかの方法である必要があります。

- **電話システム** のライセンスを持つオンラインのユーザーとして、エンタープライズ ボイスまたは 通話の計画を有効にします。

  > [!NOTE]
  > オンラインにいる人が、組織内への呼び出しをリダイレクトするのには、**電話システム**のライセンスが必要しエンタープライズ VoIP を有効にすることも計画を呼び出します。 [ビジネス ライセンスの割り当ての Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)または[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。

 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次を実行します。

- **電話システム** ライセンスおよび通話プランを取得しているオンラインユーザーは、計画を呼び出すと、Office 365 グループ、有効なメールの分配リスト、またはセキュリティ グループに追加されます。 分配リストまたはセキュリティグループに追加された新しいエージェントは、通話キューからの受信を開始するのには最大 30 分かかる場合があります。 新しく作成した分配リストまたはセキュリティ グループでは、通話キューで使用可能になるまで最大で48時間を要する場合があります。 新しく作成された Office 365 グループは、ほぼ瞬時にご利用可能です。

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![ナンバー 2](media/sfbcallout2.png)

**ルーティングの方法**呼び出しキューの配布方法を**アテンダント**、**シリアル**、または**ラウンド ロビン方式**を選択できます。 新規および既存のすべての通話キューは、応答のルーティングが既定値で選択されます。 応答のルーティングを使用すると、キューの最初の呼び出しはリング コール エージェントのすべてを同時に。 呼び出しを取得する最初の呼び出しエージェントは、呼び出しを取得します。

- **応答ルーティング**の呼び出しのすべてのエージェントを同時にリングにキュー内の最初の呼び出しが発生します。 呼び出しを取得する最初の呼び出しエージェントは、呼び出しを取得します。
- **シリアル ルーティング**着信呼び出しエージェントによって 1 つのコール エージェント] ボックスの一覧の先頭から開始するのには、着信呼び出しが発生します。 エージェントが退出中、または応答しない場合、リスト上の次のエージェントを呼び出し、キューで待機中の発信が応答するかタイムアウトになるまで、すべてのエージェントの呼び出しを 1 件ずつ試みます。
  > [!NOTE]
  > **オフライン**中、**取り込み中**表示、またはこのキューからの着信を **オプトアウト** したエージェントは、シリアルルーティングからスキップされます。
- **ラウンド ロビン方式**では、各担当者は、キューから同じ呼び出しの数を取得できるように、着信通話のルーティングを分散します。 着信呼び出しのすべてのエージェントの間で平等な機会を確保するために販売環境で非常に望ましいことがあります。

### <a name="select-an-agent-opt-out-option"></a>エージェントのオプトアウトのオプションを選択する

![オプトアウトするエージェントのチェック ボックスの表示](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![ナンバー 1](media/sfbcallout1.png)

**エージェント オプトアウト オプション** **エージェントのオプトアウト オプション**選択して特定のキューからの着信をオプトアウトすることができます。

このオプションを有効にすると、このキュー内のすべてのエージェントを開始または停止するのには、この呼び出しキューからの呼び出しを受信するには使用できます。 チェックボックスの削除することによっていつでもオプトアウトの取消しが可能で、オプトアウトされたエージェントはこの通話キューへ自動的にもう一度オプトインされます。 (すべてのエージェントの初期設定)

エージェントは次の操作を行うと、オプトアウトのオプションにアクセスできます:

 1. Skype for Business クライアントデスクトップで、 **オプション** を開きます。
 2. **[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。
 3. ユーザー設定ページで、 **通話キュー**をクリックし、次にオプトアウトしたいキューのチェック ボックスを削除します。

    > [!NOTE]
    > 以外のアプリケーションまたはエンドポイントを使用してエージェント ビジネス用デスクトップの Skype からアクセスできる、opt オプションをユーザー設定のポータル[https://aka.ms/cqsettings](https://aka.ms/cqsettings)。

![2](media/sfbcallout2.png)
**エージェント ・ アラートの設定**

これはシリアル ポートの前に呼び出しの通知エージェントの期間を定義またはラウンド ロビンのルーティング方法は、次のエージェントに移動します。

既定の設定は 30 秒ですが、最大 3 分間に設定できます。

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>処理オプションを使用した呼び出しのオーバーフローやタイムアウトの設定します。

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![1](media/sfbcallout1.png)

**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。 デフォルトは 50 ですが、それの範囲は 0 から 200 です。 この制限に達すると、通話は次の [ **呼び出しの最大数に達した場合**] 設定で指定した方法で処理されます。

* * *

![ナンバー 2](media/sfbcallout2.png)

**呼び出しの最大数に達したとき**呼び出しキューでは、(**キューの最大数を呼び出す**設定を使用して設定) の最大のサイズに達すると、新しくかかってきた呼び出しの動作を選択します。

- **切断** 通話は切断されます。
- **リダイレクト**これを選択するときは、次のいずれかを選択します。

  - **社内のユーザー** **電話システム** のライセンスを持つオンラインのユーザーそしてエンタープライズ ボイス を有効にするか通話プランを取得する必要があります。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うは、 **、会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。

  ボイスメールに必要なライセンスについては、[クラウドのボイス メールの設定](set-up-phone-system-voicemail.md)を参照してください。

  - **音声アプリケーション**呼び出しキューのいずれかの名前を選択または自動アテンダントが既に作成されています。

* * *

![ナンバー 3](media/sfbcallout3.png)

**の呼び出しのタイムアウト: 最大待機時間**できます、キュー内の保留中の呼び出しにかかった時間は、前にタイムアウトし、リダイレクトするか、切断する必要があります。 リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。 0 から 45 分に設定できます。

タイムアウト値は秒単位で、 15 秒間隔で設定することができます。 これにより、通話フローを細かく操作することができます。 たとえば、ディレクトリ検索の自動応答を 30 秒以内に、エージェントが応答しないすべての呼び出しを移動することを指定できます。

![ナンバー 4](media/sfbcallout4.png)

**呼び出しがタイムアウトしたとき**呼び出しは、**呼び出しがキューで待機できる時間**の設定で設定した制限に達すると、この呼び出しの動作を選択できます。

- **切断** 通話は切断されます。
- **呼び出しをリダイレクトします。** これを選択するとこれらのオプションが用意されます。
  - **社内のユーザー** **電話システム** のライセンスを持つオンラインユーザーで、エンタープライズ ボイス が有効化されているまたは、通話プランを取得済みである必要があります。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うは、 **、会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。

  ボイスメールに必要なライセンスについては、[クラウドのボイス メールの設定](set-up-phone-system-voicemail.md)を参照してください。

  - **音声アプリケーション**呼び出しキューのいずれかの名前を選択または自動アテンダントが既に作成されています。

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>発信呼のユーザーの呼び出し元の ID を変更します。 

**新規 CsCallingLineIdentity**コマンドレットを使用してポリシーを作成して代わりに呼び出しキュー、自動応答、または、サービス番号への発信コールを呼び出し側の ID を変更することによって、ユーザーの id を保護できます。

これを行う場合は、次を実行します。

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

**Grant-CallingLineIdentity** コマンドレットを使用してユーザーのポリシーを適用します。 これを行う場合は、次を実行します。
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

[呼び出し元 ID 利用する方法、組織内](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization)の記事で、組織内の呼び出し元 ID の設定を変更する方法の詳細を取得できます。
  
## <a name="want-to-know-more"></a>詳細情報

Windows PowerShell を使用して通話キューを作成し、設定することもできます。
  
### <a name="call-queue-cmdlets"></a>通話キューのコマンドレット

通話キューの管理で必要なコマンドレットを以下に示します。
  
- [新しい-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [セット CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [削除 CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細について

- Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。 Windows PowerShell では、Office 365 と一元管理を行う複数のタスクがある場合、日常的な作業を簡素化するを使用してマイクロソフトのチームを管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Office 365 PowerShell を使用する必要がある理由](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなどのマイクロソフトのチーム管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。

  - [Windows PowerShell では、Office 365 を管理します。](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Windows PowerShell 用にコンピューターをセットアップする](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>関連項目

[Office 365 での電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新しい-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
