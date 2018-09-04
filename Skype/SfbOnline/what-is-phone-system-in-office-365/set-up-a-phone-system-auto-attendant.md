---
title: 電話システムの自動応答をセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: '組織における効率的な通話のハンドリングのために、電話システム (クラウド PBX) の自動応答をセットアップしてテストする方法について説明します。 '
ms.openlocfilehash: fb35e36e7d59a3d47584fd15e592f68dd3ac4ae5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780465"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>電話システムの自動応答をセットアップする

自動応答により、発信者は組織に発信して、適切な部署、コール キュー、担当者、またはオペレーターに繋がるようにメニュー システムを操作できます。Skype for Business 管理センターを使用して、組織の自動応答を作成することができます。新しい自動応答を作成するには、左側のナビゲーションの [**通話ルーティング**] を開き、[**自動応答**]  >  [**新しく追加**] の順に選択してください。
  
自動応答の詳細をご覧になりたい場合は、「[電話システムの自動応答について](/microsoftteams/what-are-phone-system-auto-attendants)」を参照してください。
  
## <a name="step-1---getting-started"></a>ステップ 1 - はじめに

- 自動応答を作成してセットアップする前に、有料または無料サービス電話番号を取得するか、既存の電話番号を移行する必要があります。有料または無料サービス電話番号を取得したら、[**Skype for Business 管理センター**]  >  [**音声**]  >  [**電話番号**] ページに表示されます。サービス電話番号を取得するには、「[Skype for Business と Microsoft Team 用にサービス電話番号を取得する](getting-service-phone-numbers.md)」を、または既存のサービス電話番号を移行したい場合は、「[電話番号を Office 365 に移行する](/microsoftteams/transfer-phone-numbers-to-office-365)」を参照してください。**ユーザー (契約者)** の電話番号は自動応答に割り当てることはできません。米国外にお住いの場合は、Skype for Business 管理センターを使用してサービス電話番号を取得することはできません。その場合は[こちら](/microsoftteams/manage-phone-numbers-for-your-organization)を参照してください。
    
    > [!CAUTION]
    > 無料電話番号を取得するには、コミュニケーション クレジットをセットアップする必要があります。 これを行うには、「[コミュニケーション クレジットについて](/microsoftteams/what-are-communications-credits)」と「[組織のコミュニケーション クレジットをセットアップする](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。 
  
- 組織には、少なくとも Enterprise E3 と、**電話システム**のライセンス、または Enterprise E5 のライセンスがある必要があります。 割り当てられた**電話システム** のユーザー ラインセンスの数は、自動応答に使用可能な状態のサービス電話番号の数に影響を与えます。 保有できる自動応答の数は、組織で割り当てられた**電話システム**と**電話会議**ライセンスの数に依存します。 ライセンスに関する詳細については、 [こちら](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) をご覧ください。
    
    > [!TIP]
    > **電話システム**のライセンスをもつ Online ユーザーであるオペレーターまたはメニュー オプションに呼び出しをリダイレクトするには、呼び出しを Enterprise Voice で有効にするか、Office 365 の通話プランを割り当てる必要があります。 「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」を参照してください。 Windows PowerShell を使用することもできます。 たとえば、以下を実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>ステップ 2 - 新しい自動応答の作成

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**


**Skype for Business 管理センター**で、[**通話ルーティング**]  >  [**自動応答**] の順にクリックし、次に [**新しく追加**] をクリックします。
  
### <a name="edit-general-info-page"></a>一般情報の編集ページ
  
![新しい自動応答ページ 1。](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>**名前** 自動応答に対して分かりやすい表示名を付けます。 名前は必須で、空白を含む最大 64 文字を含めることができます。 この名前は [**自動応答**] タブの [ **名前**] 列に一覧表示されます。
***

![ナンバー 2](../images/sfbcallout2.png)<br/>**電話番号** この設定は省略可能です。 必要に応じて、自動応答の電話番号を選択します。 組織で保有している任意の利用可能なサービス有料電話番号またはサービス無料電話番号を選択できます。 一覧表示される電話番号がない場合は、サービス有料電話番号またはサービス無料電話番号を取得する必要があります。 [こちら](getting-service-phone-numbers.md)で取得してください。 <br/> <br/>

> [!NOTE]
> **ユーザー (契約者)** の番号は自動応答に割り当てることはできません。
    
***
![ナンバー 3](../images/sfbcallout3.png)<br/>**タイム ゾーン** 自動応答にはタイム ゾーンを設定する必要があります。ただし、組織のメイン アドレスのタイム ゾーンと一致している必要はありません。各自動応答には、異なるタイム ゾーンを設定できます。自動応答の営業時間の設定は、ここで選択したタイムゾーンに基づきます。
***
![14](../images/sfbcallout4.png)<br/>**言語** 自動応答で使用する言語を、一覧表示された利用可能な言語から選択します。ここで設定した自動応答の言語は、この自動応答への発信者との対話で使用されます。すべてのシステム プロンプトもこの言語で再生されます。
***
![ナンバー 5](../images/sfbcallout5.png)<br/>**音声認識** 音声認識が利用可能です。このオプションを有効にすると、発信者は設定済みの言語で音声入力を使用できます。発信者が電話機のキーパッドのみを使用できるようにしたい場合は、音声認識オプションのチェックマークをはずして音声認識を無効にすることができます。
***
![ナンバー 6](../images/sfbcallout6.png)<br/>**オペレーター** このオプションは省略可能で、自動応答で設定する必要はありません。 ただし、発信者がメニューから離れて、オペレーターと話してヘルプを受けられるようにするために、[**オペレーター**] オプションを設定できます。 <br/> <br/> オペレーターには、キー 0 が自動的に割り当てられます。 <br/> <br/> このセットアップをした場合、発信者に、[**営業時間の通話ハンドリング**] ページの [**メニュー オプションの編集**] で利用可能なオプションであることを伝える必要もあります。 自動応答でオペレーターを設定する場合は、 [**発信者が聞く内容**] ボックスに、対応するプロンプト テキストを入力するか、オーディオ ファイルを変更して、このオプションを含める必要があります。 たとえば、「オペレーターに繋ぐには、0 を押してください。」などです。 <br/><br/>  次の項目のいずれかをオペレーターとして設定できます。 
*    Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。 <br/>

        > [!Note] 
        > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。 Lync Server 2010 はサポートされていません。 <br/> 

*    セットアップ済みの **コール キュー**です。 
*    発信者がボイスメールに送られるようにセットアップできます。 このセットアップを行うには、[**社内のユーザー**] を選択して、そのユーザーの呼び出しが直接ボイスメールに転送されるように設定します。 
   
### <a name="select-hours-of-operation-page"></a>営業時間の選択ページ

既定では、営業時間は 1 日 24 時間、週 7 日に設定されているため、すべての時間が営業時間と見なされます。 営業時間に含まれない時間はすべて、営業時間後と見なされます。 [**カスタム**] オプションを選択して、営業時間を設定すると、[ **営業時間外後の通話処理**] という新しいページが追加され、自動応答の営業時間外の通話処理を設定できます。
  
![新しい業務時間の自動応答です。](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![ナンバー 1](../images/sfbcallout1.png)<br/>カレンダーで特定の営業時間を選択するには、[ **カスタム**] オプションを選択します。[ **カスタム**] を選択すると、既定により、営業時間が月曜日から金曜日の午前 9:00 から午後 5:00 に設定されます。
***
![ナンバー 2](../images/sfbcallout2.png)<br/>営業時間を変更するには、予定表を使用して設定したい営業時間を選択してください。 予定表を使用すると、30 分間隔で営業時間を選択できます。ここで選択する営業時間は、[**全般情報**] ページで設定したタイム ゾーンに基づいて設定されます。 休憩 (昼食休憩など) を設定するには、選択解除するか、カレンダーの時間を選択解除にドラッグします。 営業時間内に複数の休憩時間を設定できます。 
   
### <a name="select-business-hours-call-handling-page"></a>営業時間の通話処理選択ページ

> [!TIP]
> カスタムの営業時間スケジュールを使用する場合は、営業時間外の通話処理を設定する必要があります。[ **営業時間外後の問い合わせ対応**] ページが追加されるので、そこでこのオプションを構成できます。このページには、[ **営業時間の問い合わせ対応**] と同じオプションが表示されます。 
  
発信者が組織の自動応答の電話番号に対して営業時間内に発信してきた場合に流れる応答メッセージ、プロンプト、メニューを設定できます。
  
![営業時間の通話処理です。](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>**会社の応答メッセージ** 営業時間の応答メッセージは省略可能で、[**なし**] に設定できます。 この場合、発信者には選択したオプションによって通話が処理されるまでメッセージまたは応答メッセージは再生されません。 オーディオ ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げ機能を使用してカスタムの応答メッセージを作成することもできます。
*    **なし** 自動応答電話番号に発信しても応答メッセージは再生されません。
*    **カスタムの応答メッセージを作成** このオプションを選択する場合は、システムが読み上げるテキスト (1000文字以内) を入力します。 たとえば、「Contoso へようこそ。 お電話ありがとうございます。」 などと、[**発信者が聞く内容**] ボックスに入力できます。
*    **音声ファイルをアップロード** このオプションを選択する場合は、応答メッセージを録音して、音声ファイル (.wav, .mp3 または .wma 形式) をアップロードしてください。
***
![ナンバー 2](../images/sfbcallout2.png)<br/>営業時間中に着信する呼び出しに対する動作内容を選択できます。 次のオプションから選択できます。
*    **切断** これを選択すると、発信者が営業時間の応答メッセージを聞いた後に切断されます。
*    **呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。
     *    Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。 発信者がボイス メールに送信されるようにセットアップすることができます。 これを行うには、**[社内の担当者]** を選択して、そのユーザーの呼び出しが直接ボイス メールに転送されるように設定します。 <br/><br/>   
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
    - Enterprise Voice で有効になっているか、Office 365 の通話プランを割り当てられている、**電話システム**のライセンスをもつ**社内の担当者**  発信者がボイス メールに送信されるようにセットアップすることができます。 これを行うには、**[社内の担当者]** を選択して、そのユーザーの呼び出しが直接ボイス メールに転送されるように設定します。<br/><br/> 
    
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
![ナンバー 2](../images/sfbcallout2.png)<br/>**休業日の応答メッセージ** 休業日の応答メッセージは省略可能であり、[**なし**] に設定することができます。 この場合、選択したオプションの 1 つで処理される呼び出しの前に、メッセージや応答メッセージが発信者に対して流れることはありません。 オーディオ ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げ機能を使用してカスタムの応答メッセージを作成することもできます。
*    **なし** 自動応答電話番号に発信しても応答メッセージは再生されません。
*    **カスタムの応答メッセージを作成** このオプションを選択する場合は、システムが読み上げるテキスト (1000文字以内) を入力します。 たとえば、「あけましておめでとうございます。 当社は現在、休業中です。」 などと、[**発信者が聞く内容**] ボックスに入力できます。
*    **音声ファイルをアップロード** このオプションを選択する場合は、休業日の応答メッセージを録音して、音声ファイル (.wav, .mp3 または .wma 形式) をアップロードしてください。  
***
![ナンバー 3](../images/sfbcallout3.png)<br/>**応答メッセージ後の呼び出しに対する動作** この休業日に着信する呼び出しに対する動作を選択します。 次のオプションから選択できます。
*    **切断** 休業日の応答メッセージが流れてから、通話が切断されます。
*    **呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。
     *    Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。 発信者がボイス メールに送信されるようにセットアップすることができます。 これを行うには、**[社内の担当者]** を選択して、そのユーザーの呼び出しが直接ボイス メールに転送されるように設定します。 <br/><br/> 
     
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
  
### <a name="select-dial-scope-page"></a>ダイヤル スコープ選択ページ

このページでは、ディレクトリに一覧表示されるユーザーと、発信者が組織に発信するときに名前によるダイヤルで発信可能なユーザーをセットアップすることができます。
  
![名前によるダイヤルを使用した検索のダイヤル スコープ](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>[**含める**] オプションを使用すると、2 つのオプションがあります。
*    **すべての Online ユーザー** このオプションを使用すると、組織のすべてのユーザーがディレクトリ検索に含められます。 **電話システム** のライセンスをもつすべての Online ユーザーと、Office 365 の通話プランをもつ、Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーが一覧表示されます。 
*    **カスタム** このオプションを使用すると、組織内で作成された Office 365 グループ、配布リスト、またはセキュリティ グループ、さらにこの Office 365 グループ、配布リスト、またはセキュリティ グループに追加された、**電話システムのライセンスをもつ Online ユーザー**または Skype for Business Server 2015 あるいは Lync Server 2013 を使用してオンプレミスでホストされた人を検索することができます。 複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。 <br/><br/> 

    > [!Caution]
    > Lync Server 2010 の展開からのオンプレミスのユーザーは、名前によるダイヤルを使用してディレクトリを検索しても一覧表示されません。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>[**除外する**] オプションを使用すると、2 つのオプションがあります。
*    **なし** このオプションを使用すると、いずれの Online ユーザーもディレクトリ検索から除外されないと表示されます。 
*    **カスタム** このオプションを使用すると、組織内で作成された Office 365 グループ、配布リスト、セキュリティ グループ、さらに Office 365 グループ、配布リスト、セキュリティ グループに追加されたすべての人が、ディレクトリ検索から除外されます。 複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。 <br/><br/> 

    > [!Caution]
    > Lync Server 2010 の展開からのオンプレミスのユーザーは、名前によるダイヤルを使用してディレクトリを検索しても一覧表示されません。          
   
> [!NOTE]
> 他のユーザーが音声認識で「名前によるダイヤル」を使用した場合、新しいユーザーの名前がディレクトリに一覧表示されるまでに最長で 36 時間かかることがあります。 
  
すべての必須フィールドに入力し、通話処理のメニューとオプションをセットアップしたら、[**保存**] をクリックします。
  
## <a name="editing-and-testing-auto-attendants"></a>自動応答の編集およびテスト

自動応答を保存すると、[**自動応答**] ページに表示されます。 これにより、名前、電話番号、言語、状態など、セットアップしたオプションのいくつかをすばやく表示できます。
  
自動応答を変更する場合は、自動応答を選択し、操作ウィンドウの [**編集**] をクリックします。
  
操作ウィンドウの [**テスト**] ボタンを使用して、自動応答へのテスト通話を行うこともできます。
  
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
   
### <a name="more-about-windows-powershell"></a>Windows PowerShell についての詳細

- Windows PowerShell は、ユーザーと、ユーザーが実行できる作業範囲を管理します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell 使用する理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピックス
[Office 365 の電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
    
  
 
