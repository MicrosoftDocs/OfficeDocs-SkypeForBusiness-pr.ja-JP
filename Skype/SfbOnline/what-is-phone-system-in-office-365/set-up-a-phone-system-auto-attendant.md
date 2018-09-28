---
title: 電話システムの自動応答をセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '設定し、組織の処理効率の呼び出しに自動応答の電話システム (PBX をクラウド) をテストする方法について説明します。 '
ms.openlocfilehash: bceda290adc10e806249cbd0938305ffa321d91f
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347268"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>電話システムの自動応答をセットアップする

自動応答は、組織へのコールし、右の部門にそれらを取得するには、キュー、人、または演算子を呼び出すメニュー システムを移動するユーザーを使用できます。 ビジネス管理センターは、Skype を使用して、組織の自動応答を作成できます。 To create a new auto attendant, go to **Call routing** in the left navigation, and then select **Auto attendants** > **Add new**.
  
自動アテンダントの詳細についてはする場合を参照してください[電話システムの自動応答は何ですか?](/microsoftteams/what-are-phone-system-auto-attendants)
  
## <a name="step-1---getting-started"></a>ステップ 1 - はじめに

- 自動応答を作成しセットアップする前に、既存の有料または無料のサービス番号を取得もしくは転送する必要があります。 有料または無料のサービスの番号を取得した後にで示される**ビジネス管理センターの Skype** > **音声** > **の電話番号**のページです。 サービス番号を取得するには、 [Skype のビジネスおよびマイクロソフトのチームの取得サービスの電話番号](getting-service-phone-numbers.md)を参照するか、転送し、既存のサービス番号にする場合は、 [Office 365 に電話番号を転送する](/microsoftteams/transfer-phone-numbers-to-office-365)を参照してください。 **User (subscriber)** numbers can't be assigned to auto attendants. 米国以外の場合は、サービス番号を取得するビジネス管理センターの Skype を使うことはできません。移動[ここでは](/microsoftteams/manage-phone-numbers-for-your-organization)代わりにします。

    > [!CAUTION]
    > 取得し、フリー ダイヤル電話番号を使用して、通信のクレジットを設定する必要があります。 この参照を行うに[通信のクレジットは何ですか?](/microsoftteams/what-are-communications-credits)し、[組織の通信のクレジットを設定](/microsoftteams/set-up-communications-credits-for-your-organization)。
  
- 組織は、エンタープライズの E3 と**電話システム**のライセンスまたはエンタープライズ E5 のライセンス (最低) が必要です。 自動応答に使用する利用可能なサービス番号の番号を割り当てられている**電話システム**のユーザー ライセンスの数に影響します。 ことが自動応答の数は、組織に割り当てられている番号の**電話システム**と**オーディオ会議**ライセンスに依存します。 ライセンスに関する詳細については、 [こちら](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) をご覧ください。
    
    > [!TIP]
    > 演算子または**電話システム**のライセンスを持つオンラインのユーザーは、メニュー ・ オプションへの呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするか、Office 365 のプランを呼び出すことを割り当てることにする必要があります。 「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。 Windows PowerShell を使用することもできます。 などを実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>ステップ 2 - 新しい自動応答の作成

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**


**Skype for Business 管理センター**で、[**通話ルーティング**]  >  [**自動応答**] の順にクリックし、次に [**新しく追加**] をクリックします。
  
### <a name="edit-general-info-page"></a>[一般情報の編集] ページ
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>**名**自動アテンダントのわかりやすい表示名を入力します。 名前の入力は必須で、空白を含む最大 64 文字を含めることができます。 この名前は [ **自動応答**] タブの [ **名前**] 列に表示されます。
***

![ナンバー 2](../images/sfbcallout2.png)<br/>**電話番号** この設定は省略可能です。 必要に応じて、自動応答の電話番号を選択します。 任意の利用可能なサービスの有料または無料電話番号が組織のあるを選択することができます。 電話番号が一覧表示されない場合は、サービスの有料またはフリーダイヤルの電話番号を取得する必要があります。 [こちら](getting-service-phone-numbers.md)で取得してください。 <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![ナンバー 3](../images/sfbcallout3.png)<br/>**タイム ゾーン** 自動応答にはタイム ゾーンを設定する必要があります。ただし、組織のメイン アドレスのタイム ゾーンと一致している必要はありません。各自動応答には、異なるタイム ゾーンを設定できます。自動応答の営業時間の設定は、ここで選択したタイムゾーンに基づきます。
***
![14](../images/sfbcallout4.png)<br/>**言語** 自動応答に使用する言語を、一覧表示されている使用可能な言語の中から選択します。 ここで設定した言語は、この自動の応答へのコールの人と対話する自動応答を使用し、この言語ですべてのシステム プロンプトが再生する言語です。
***
![ナンバー 5](../images/sfbcallout5.png)<br/>**音声認識** このオプションが選択されていると、音声認識を使用できます。 電話してきた人は、設定した言語で音声入力を使用できます。 発信者に、電話のキーパッドのみを使用してほしい場合は、それをオフにして音声認識機能を無効にできます。
***
![ナンバー 6](../images/sfbcallout6.png)<br/>**オペレーター** このオプションは省略可能で、自動応答で設定する必要はありません。 ただし、電話することを支援してくれる人に話をするメニューを解除することをする人の**オペレーター**のオプションを設定できます。 <br/> <br/> オペレーターには、キー 0 が自動的に割り当てられます。 <br/> <br/> このセットアップをした場合、発信者に、[**営業時間の通話ハンドリング**] ページの [**メニュー オプションの編集**] で利用可能なオプションであることを伝える必要もあります。 自動応答でオペレーターを設定する場合は、 [**発信者が聞く内容**] ボックスに、対応するプロンプト テキストを入力するか、オーディオ ファイルを変更して、このオプションを含める必要があります。 たとえば、「オペレーターに繋ぐには、0 を押してください。」などです。 <br/><br/>  次の項目のいずれかをオペレーターとして設定できます。 
*    Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。 <br/>

        > [!Note] 
        > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。 Lync Server 2010 はサポートされていません。 <br/> 

*    設定済みの **通話キュー**。 
*    発信者がボイスメールに送られるように設定できます。 これを行うには、**あなたの会社の担当者**を選択し、ボイスメールに直接転送するのにはこのメンバーの呼び出しを設定します。 
   
### <a name="select-hours-of-operation-page"></a>営業時間の選択ページ

既定では、営業時間内に設定されます、1 日、週 7 日 24 時間すべての時間は営業時間内と見なされるため。 営業時間に含まれない時間は営業時間外として考慮されます。 [**カスタム**] オプションを選択し、[会社の就業時間を設定して場合、**時間処理の呼び出し後**に呼び出される新しいページ追加されます、自動アテンダント業務時間終了後の処理の呼び出しを構成することができます。
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![ナンバー 1](../images/sfbcallout1.png)<br/>カレンダーで特定の営業時間を選択するには、[ **カスタム**] オプションを選択します。[ **カスタム**] を選択すると、既定により、営業時間が月曜日から金曜日の午前 9:00 から午後 5:00 に設定されます。
***
![ナンバー 2](../images/sfbcallout2.png)<br/>営業時間を変更するには、予定表を使用して設定したい営業時間を選択してください。 予定表を使用すると、30 分間隔で営業時間を選択できます。ここで選択する営業時間は、[**全般情報**] ページで設定したタイム ゾーンに基づいて設定されます。 休憩 (昼食休憩など) を設定するには、選択解除するか、カレンダーの時間を選択解除にドラッグします。 営業時間内に複数の休憩時間を設定できます。 
   
### <a name="select-business-hours-call-handling-page"></a>営業時間の通話処理選択ページ

> [!TIP]
> カスタムの営業時間スケジュールを使用する場合は、営業時間外の通話処理を設定する必要があります。[ **営業時間外後の問い合わせ対応**] ページが追加されるので、そこでこのオプションを構成できます。このページには、[ **営業時間の問い合わせ対応**] と同じオプションが表示されます。 
  
その人が勤務時間中に、組織の自動応答の電話番号への呼び出しが聞こえますごきげんよう、プロンプト、およびメニューを設定できます。
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>**応答メッセージ** 営業時間の応答メッセージは省略可能で、[ **なし**] に設定できます。 この場合、発信者には選択したオプションによって通話が処理されるまでメッセージまたは応答メッセージは再生されません。 音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。
*    **なし**自動アテンダントの電話番号への人を呼び出すには、あいさつ文は再生されません。
*    **作成するカスタムの案内応答**このオプションを選択する場合は、(1000 文字以内) を読み取るシステムを設定するテキストを入力します。 たとえば、「Contoso へようこそ。 お電話ありがとうございます。 などと、[**発信者が聞く内容**] ボックスに入力できます。
*    **オーディオ ファイルをアップロード**これを選択する場合は、あいさつ文を記録し、オーディオ (.wav、.mp3 や .wma 形式) でファイルをアップロードしています。
***
![ナンバー 2](../images/sfbcallout2.png)<br/>営業時間中に着信する呼び出しに対する動作内容を選択できます。 次のオプションから選択できます。
*    **切断** これを選択すると、発信者が営業時間の応答メッセージを聞いた後に切断されます。
*    **呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。
     *    Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うには、**社内の担当者**を選択しの呼び出しは、ボイスメールに直接転送するには、このユーザーを設定します。 <br/><br/>   
        > [!Note]
        > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。 Lync Server 2010 はサポートされていません。 <br/><br/>

     *    **コール キュー** コール キューを使用すると、セットアップ済みの既存のコール キューに、呼び出しが転送されます。
     *    別の **自動応答** 既存の自動応答を使用して、サブ メニューを含むメニュー オプションの 2 番目のレベルを作成できます。 これらは入れ子の自動応答と呼ばれます。
*    **メニュー オプションのプロンプトを再生** これらを使用して、再生したいプロンプトを設定することもできます。
***
![ナンバー 3](../images/sfbcallout3.png)<br/>**メニュー プロンプト** メイン メニュー プロンプトを作成するには、テキスト読み上げを使用するか、音声ファイル (.wav, .mp3 または .wma) をアップロードできます。[ **発信者にはこのように聞こえます**] ボックスにプロンプトを入力できます。また、たとえば「セールスの場合は 1 を押すか、1 と言ってください。サービスの場合は 2 を押すか、2 と言ってください。カスタマー サポートの場合は 3 を押すか、3 と言ってください。オペレーターの場合は 0 を押すか、0 と言ってください。このメニューをもう一度お聞きになりたい場合は、アスタリスク キーを押すか、リピートと言ってください。」という音声ファイルを録音できます。 **カスタム プロンプトを作成** このオプションを選択する場合は、システムが読み上げるテキスト (最大 1000 文字) を入力する必要があります。 **音声ファイルをアップロード** このオプションを選択する場合は、応答メッセージを録音して、音声ファイル (.wav, .mp3 または .wma 形式) をアップロードする必要があります。
***
![ナンバー 4](../images/sfbcallout4.png)<br/>**名前によるダイヤル** このオプションを選択すると、発信者はディレクトリ検索を使用して組織内の人を検索することができます。 [**ダイヤル スコープ**] ページでこれらのオプションをセットアップすることにより、名前によるダイヤルで誰が対応可能または対応不可として一覧表示されるのかを選択することができます。 **電話システム** のライセンスをもつオンライン ユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされているユーザーであれば、名前によるダイヤルで探すことができます。<br/><br/>  

> [!WARNING]
> Lync 2010 を使用してオンプレミスでホストされているユーザーは名前によるダイヤルで**探すことはできません**。
***

![ナンバー 5](../images/sfbcallout5.png)<br/>**メニューの編集オプション** メニュー オプションはキーパッドのキー ボタンを使用して追加または削除できます。 メニュー オプションを追加するには、キーパッド上の対応するキーを押します。 使用中のキーは色が変更され、対応するオプションの行が下に表示されます。 メニュー オプションを削除するには、単にキーパッド コントロール上の対応するキーをクリックして、このキーの選択を解除します。 キー マッピング行が削除されます。<br/><br/>  **ヒント:** 削除オプションに追加する場合には、メニュー プロンプト テキストを更新するか、音声を別に再録音する必要があります。既存のメニュー プロンプトに対しては自動的に実行されないためです。  <br/><br/>  メニュー オプションはどのような順番でも追加、削除でき、キー マッピングは連続的である必要はありません。 たとえば、キー 2 を使用せず、キー 0、1、3 をオプションにマッピングしてメニューを作成することが可能です。<br/><br/> 

> [!NOTE]
> キー * (繰り返し) と # (戻る) は、システムによって予約されており、再割り当てすることはできません。 音声認識が有効になっている場合、* を押すと「繰り返し」、# を押すと「戻る」の音声コマンドに対応します。


メニュー オプションをセットアップするには、キーを選択した後、以下を実行する必要があります。 
- **オプションの名前を入力** 最大 64 文字を入力でき、「顧客サービス」 または 「オペレーションとグラウンド」のように複数の単語を含めることができます。 音声認識を有効にしている場合は、名前は自動的に認識されます。発信者は 3 を押すか、「さん」と音声入力するか、または 「顧客サービス」 と音声入力して、キー 3 にマッピングされたオプションを選択することができます。 
- 次の手順で、対応するキーを押した場合に呼び出しが送信される場所を選択するか、音声認識を使用すればオプションが選択されます。 次の場所に呼び出しを送信できます。 
    - **オペレーター** オペレーターがすでにセットアップされている場合は、キー 0 に自動的にマッピングされますが、削除するか別のキーに割り当てることもできます。 オペレーターがどのキーにも設定されていない場合は、音声コマンド 「オペレーター」 も無効になります。 
    - Enterprise Voice で有効になっているか、Office 365 の通話プランを割り当てられている、**電話システム**のライセンスをもつ**社内の担当者** 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うには、**社内の担当者**を選択しの呼び出しは、ボイスメールに直接転送するには、このユーザーを設定します。<br/><br/> 
    
        > [!Note] 
        > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。 Lync Server 2010 はサポートされていません。 <br/><br/>

    - **コール キュー** コール キューを使用すると、セットアップ済みの既存のコール キューに、呼び出しが転送されます。 
    - **自動応答** 既存の自動応答を使用して、サブ メニューを含むメニュー オプションの 2 番目のレベルを作成できます。 これらは入れ子の自動応答と呼ばれます。<br/><br/>
    
        > [!Note]
        > 入れ子 (または第 2 レベル) の自動応答の **営業時間** も使用されます。これには、セットアップされた他の自動応答から送信された呼び出しへ向けたものも含まれます。         
   
### <a name="select-holidays-page"></a>休業日選択ページ 

各自動応答には、最大 20 個の決められた休業日を追加できます。
  
![自動応答で休業日をセットアップする](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>**休業日を追加** 「**休業日名** 」フィールドに、新しい休業日の名前を入力します。<br/><br/> 休業日名は最大 64 文字で構成でき、同じ自動応答に対して一意である必要があります。 たとえば、同じ自動応答で 「感謝祭」という名前の休業日を 2 つもつことはできません。  
***
![ナンバー 2](../images/sfbcallout2.png)<br/>**休業日の応答メッセージ** 休業日の応答メッセージは省略可能であり、[**なし**] に設定することができます。 この場合、発信者には選択したオプションによって通話が処理されるまでメッセージまたは応答メッセージは再生されません。 音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。
*    **なし**自動アテンダントの電話番号への人を呼び出すには、あいさつ文は再生されません。
*    **作成するカスタムの案内応答**このオプションを選択する場合は、(1000 文字以内) を読み取るシステムを設定するテキストを入力します。 たとえば、「あけましておめでとうございます。 当社は現在、休業中です。」 などと、[**発信者が聞く内容**] ボックスに入力できます。
*    **オーディオ ファイルをアップロード**これを選択する場合は、時候のあいさつを記録し、オーディオ (.wav、.mp3 や .wma 形式) でファイルをアップロードしています。  
***
![ナンバー 3](../images/sfbcallout3.png)<br/>**応答メッセージ後の呼び出しに対する動作** この休業日に着信する呼び出しに対する動作を選択します。 次のオプションから選択できます。
*    **切断** 休業日の応答メッセージが流れてから、通話が切断されます。
*    **呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。
     *    Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うには、**あなたの会社の人**を選択し、この人を通話をボイスメールに直接転送します。 <br/><br/> 
     
         > [!Note] 
         > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。 Lync Server 2010 はサポートされていません。<br/><br/>

     *    セットアップ済みの既存のコール キューに対する呼び出しを転送するための**コール キュー**。
     *    サブメニューを含むメニュー オプションの2 番目のレベルを作成するための別の**自動応答**。 これらは入れ子の自動応答と呼ばれます。 <br/><br/>
     
         > [!Note]
         > 既定では、休業期間中に着信したすべての呼び出しは、応答メッセージの後に切断されます。よって、違うビヘイビアーが望ましい場合には、リダイレクトを指定する必要があります。

***
![ナンバー 4](../images/sfbcallout4.png)<br/>**休業日の開始と終了を設定する方法** dd/mm/yyyy の形式で、休業日の開始日を入力し、日付範囲テーブルに表示されたとおりに、開始時刻、終了日、終了時刻を選択します。<br/><br/>1 つの休業日に対して、最大 10 個の違う日付範囲を指定できます。 たとえば、大晦日の休業日の日付範囲を最大 10 年分追加することができます。 休業日は、複数日にまたがることができます。<br/><br/>さらに休業日の日付範囲 (たとえば、翌年分) を追加するには、[**さらに追加**] をクリックし、休業日の新しい開始日と終了日を入力してください。<br/><br/>入れ子になった休日もサポートされています。 たとえば、1 つの「休業期間」のタイム フレーム内で複数の休日を入れ子にできます。 
*    **12 月 24日から 1 月 3 日:** 「よい休日をお過ごしください。 当社は現在、お休みをいただいております。 1 月 4 日に営業を再開します。」
*    **12 月 25 日:** 「メリークリスマス！ 当社は現在、お休みをいただいております。 1 月 4 日に営業を再開します。」
*    **1 月 1 日:**「あけましておめでとうございます。 当社は現在、お休みをいただいております。 1 月 4 日に営業を再開します。」
   
自動応答を保存すると、休業日が [**休業日**] タブに表示され、休業日の設定を編集、追加、修正できます。
  
### <a name="select-dial-scope-page"></a>ダイヤルの範囲を選択ページ

このページには、組織内のどのユーザーになりますディレクトリに一覧表示されているとダイヤルの利用可能な場合で組織を呼び出す人の名前でを設定することができます。
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>[ **含める**] オプションには次の 2 つのオプションがあります。
*    **すべての Online ユーザー** このオプションを使用すると、組織のすべてのユーザーがディレクトリ検索に含められます。 **電話システム** のライセンスをもつすべての Online ユーザーと、Office 365 の通話プランをもつ、Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーが一覧表示されます。 
*    **カスタム** このオプションを使用すると、組織内で作成された Office 365 グループ、配布リスト、またはセキュリティ グループ、さらにこの Office 365 グループ、配布リスト、またはセキュリティ グループに追加された、**電話システムのライセンスをもつ Online ユーザー**または Skype for Business Server 2015 あるいは Lync Server 2013 を使用してオンプレミスでホストされた人を検索することができます。 複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。 <br/><br/> 

    > [!Caution]
    > オンプレミス ユーザーが Lync Server 2010 の展開は、名前が他のダイヤルを使用してディレクトリを検索すると表示されません。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>**除外**オプションを使用すると、2 つのオプションがあります。
*    **なし** このオプションを使用すると、いずれの Online ユーザーもディレクトリ検索から除外しません。 
*    **カスタム**このオプションを使用する場合、Office 365 のグループ、配布リスト、または組織内で作成されたセキュリティ グループを検索することができますおよびすべてのユーザーが Office 365、そのグループに配布リストを追加またはセキュリティ グループは、ディレクトリ検索から除外されます。 複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。 <br/><br/> 

    > [!Caution]
    > オンプレミス ユーザーが Lync Server 2010 の展開は、名前が他のダイヤルを使用してディレクトリを検索すると表示されません。          
   
> [!NOTE]
> ディレクトリに一覧表示、ダイヤルを使用するときに名前で音声認識でその名前を持つ新しいユーザーには、最大で 36 時間がかかる場合があります。 
  
すべての必須フィールドに入力して、メニューとオプションを処理する呼び出しを設定して後、は、**保存**をクリックします。
  
## <a name="editing-and-testing-auto-attendants"></a>編集と自動応答をテストします。

自動応答を保存すると、[ **自動応答**] ページに表示されます。 これによって、迅速にいくつかのオプションを設定するなどの名前、電話番号、言語、およびステータスを参照してください。
  
自動応答を変更する場合は、自動応答を選択し、操作ウィンドウの [**編集**] をクリックします。
  
アクション ペインで、[**テスト**] ボタンを使用して、自動アテンダントをテストの呼び出しも簡単に配置できます。
  
## <a name="want-to-know-more"></a>詳細情報

Windows PowerShell を使用して自動応答を作成し、設定することもできます。
  
### <a name="auto-attendant-cmdlets"></a>自動応答のコマンドレット

自動応答で管理する必要があるコマンドレットを以下に示します。
  
||| 
|---|---|
[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                                                      | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                                              |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                                                      | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                                                   | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                                                                 | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                                              |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                                                                  |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                                                     | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                                                     | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細について

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Office 365 での電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[電話システムの自動応答について](/MicrosoftTeams/what-are-phone-system-auto-attendants.md)

[小規模企業の例では、自動応答を設定](tutorial-org-aa.yml)  