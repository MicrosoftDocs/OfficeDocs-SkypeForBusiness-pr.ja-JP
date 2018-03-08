---
title: "電話システムでの自動応答を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "セットアップし、組織の処理効率的な電話への電話システムで (クラウド PBX) の自動応答をテストする方法について説明します。 "
ms.openlocfilehash: a8968200bdb4dd09bb890255e0f252663ad8887e
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-a-phone-system-auto-attendant"></a>電話システムでの自動応答を設定します。

自動応答では、組織にコールインして、それらの部門にする、キュー、人、または演算子を呼び出すメニュー システムを移動するユーザーを許可します。組織の自動応答を作成するには、Business 管理センターの Skype を使用します。新しい自動応答を作成する、左のナビゲーションで、**呼び出しのルーティング**に移動し、**自動応答**を > **新規追加**します。
  
自動応答の詳細を確認する場合を参照してください[電話システムでの自動応答は何ですか?](what-are-phone-system-auto-attendants.md) 。
  
## <a name="step-1---getting-started"></a>手順 1 - 作業の開始

- 作成して、自動応答を設定する、前にしたり、既存の有料またはフリー ダイヤルのサービスに転送する必要があります。 数値。**Skype for Business 管理センター**で表示されますが、有料またはフリー ダイヤル サービス番号したら、 > **音声** > **電話番号**] ページ。サービス番号を移動するには、 [Skype for Business とチームの Microsoft のサービス電話番号を取得](getting-service-phone-numbers.md)が表示されるまたは転送を既存のサービス番号の場合は、 [Office 365 への電話番号に転送](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)を参照してください。自動応答には、**ユーザー (サブスクライバー)**番号を割り当てることはできません。米国外の場合は、サービスの数を取得する Skype for Business 管理センターを使うことはできません。[ここ](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)にします。
    
    > [!CAUTION]
    > フリー ダイヤル電話番号を使用するをクレジットの通信を設定する必要があります。ため、このを参照してください[通信を加算したものは何ですか?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)し、[組織の通信クレジットを設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)します。 
  
- 組織は、Enterprise E3 および**電話システム**のライセンスまたは Enterprise E5 ライセンス (最低) が必要です。割り当てられている**電話システムで**ユーザーのライセンスの数では、自動応答のために利用できるサービス番号の数に反映されます。した自動応答の番号が、組織内で割り当てられている番号の**電話システム**と**電話会議**ライセンスに依存します。詳細については、ライセンス、[[次のとおり](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)です。
    
    > [!TIP]
    > 演算子または**電話システムで**ライセンスを使って、オンラインのユーザーである] メニューのオプションに通話をリダイレクトするには、エンタープライズ ボイスを有効にする、またはに Office 365 のプランの呼び出しを割り当てる必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。Windows PowerShell を使用することもできます。たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>手順 2 - 新しい自動応答を作成します。

**Skype for Business 管理センター**で、[**着信のルーティング**] をクリックします > **の自動応答**では、[**新規追加**] をクリックします。
  
### <a name="edit-general-info-page"></a>一般的な情報] ページを編集します。
  
![新しい自動応答ページ 1 です。](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>**名**自分の自動応答のわかりやすい表示名を入力します。名前は、必要なスペースも含めて、最大 64 文字を含めることができます。[**自動応答**] タブで**[名前**] 列が表示されます。
***

![数値 2](../images/sfbcallout2.png)<br/>**電話番号**この設定はオプションです。必要であれば、自動応答の電話番号を選択します。任意のサービスの利用可能な有料または組織用に所有しているフリー ダイヤル電話番号を選ぶことができます。電話番号が一覧に表示されない場合は、サービス有料またはフリー ダイヤル電話を入手する必要があります数。[[ここで](getting-service-phone-numbers.md)これらを取得します。<br/> <br/>

    > [!Note]
    > **User (subscriber)** numbers can't be assigned to auto attendants.
***
![数値 3](../images/sfbcallout3.png)<br/>**タイム ゾーン**自分の自動応答のタイム ゾーンを設定する必要がありますが、組織の住所のタイム ゾーンに対応する必要はありません。各自動応答は、別のタイム ゾーンを持つことができ、[勤務時間の自動応答の設定に設定されますに基づいてここで選択したタイム ゾーンでします。
***
![14](../images/sfbcallout4.png)<br/>**言語**利用可能な言語のいずれかから自分の自動応答の使用する言語を選択します。ここで設定した言語の言語をシステムのすべてのメッセージにその言語で再生するには、この自動応答では、ユーザーの自動応答を使用を操作するのには
***
![5](../images/sfbcallout5.png)<br/>**音声認識**音声認識機能し、このオプションがオンになっているかどうか。通話でユーザー設定した言語で音声入力を使用できます。音声認識を無効にするには、のみユーザーの電話のキーパッドを使用できるようにする場合は、それをオフにします。
***
![6](../images/sfbcallout6.png)<br/>**演算子**これは、オプションは、自動応答用に設定する必要はありません。ただし、電話を活用するためのユーザーに [読み上げ] メニューを解除することができるユーザーの**演算子**のオプションを設定できます。<br/> <br/> キー 0 は演算子に自動的に割り当てられます。 <br/> <br/> 場合は、この設定をして、ユーザーは通話これは、[**勤務時間の通話処理**] ページの**編集] メニューのオプション**で利用可能なオプションをユーザーに通知する必要もします。自動応答の演算子を設定する場合は、**相手**のボックスに、対応するメッセージのテキストを入力または変更して音声ファイルには、このオプションを含める必要があります。たとえば、"の演算子、0 キーを押します。"<br/><br/>  演算子として、次のいずれかを設定できます。 
*    エンタープライズ ボイスを有効になっている、または Office 365 のプランの呼び出しを割り当てられている**電話システムで**ライセンスを使って**社内のユーザー**にします。 <br/>

        > [!Note] 
        > オンライン ユーザーは、**社内のユーザー**または、ユーザーが内部設置型にホストされている Skype for Business Server 2015 または Lync Server 2013 を使ったします。Lync Server 2010 はサポートされていません。<br/> 

*    設定した**電話キュー**です。 
*    呼び出し先の人がボイス メールに送信されるようにをそれを設定できます。これを行うには、**社内のユーザー**を選択しを直接ボイス メールに転送するこのユーザーの呼び出しを設定します。 
   
### <a name="select-hours-of-operation-page"></a>ページの操作の時間を選択します。

既定では、すべての時間には、営業時間と見なされるため勤務時間が 24 時間年中無休] に設定します。すべての営業時間に含まれていない時間は、営業時間後と見なされます。場合は、**ユーザー設定**] オプションを選択して、営業時間を設定して、[という**時間通話処理後に**新しいページが追加されます業務時間後に自動応答の処理、通話を構成することができます。
  
![新しい自動応答の時間です。](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![数値 1](../images/sfbcallout1.png)<br/>予定表の特定の業務時間を選択する [**ユーザー設定**] オプションを選択します。**ユーザー設定**を選択すると月曜日から金曜日、既定で 9:00 ~ 5時 00分 pm 勤務時間に設定されます。
***
![数値 2](../images/sfbcallout2.png)<br/>営業時間を変更するには、予定表を使用して設定する営業時間を強調表示します。予定表では、30 分間の間隔で勤務時間を選択することができ、ここで選択した勤務時間に設定されますに基づいて**一般的な情報]**ページで設定したタイム ゾーンにします。中断 (昼休みなど) をセットアップするには、選択を解除または予定表の時間を選択解除するのにドラッグします。営業時間内で複数の区切りを設定できます。 
   
### <a name="select-business-hours-call-handling-page"></a>[勤務時間の通話処理ページ

> [!TIP]
> ユーザー設定の勤務時間のスケジュールを使用している場合は、営業時間後の処理の呼び出しを設定する必要もします。これらのオプションを構成すると、**営業時間の通話処理**と同じオプションが提供されます、**時間の通話処理後**のページが追加されます。 
  
そのユーザーが、組織の自動応答の電話番号で通話が勤務時間中に聞くあいさつ文、画面の指示、およびメニューを設定することができます。
  
![営業時間は通話処理します。](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>**会社のあいさつ文**業務時間の案内応答はオプションで、 **[なし]**に設定できます。この例では、発信者が聞くなしメッセージまたはあいさつ文を選択するオプションのいずれかを処理する前にします。(.Wav、mp3 または .wma 形式で)、音声ファイルをアップロードしたり、音声合成を使用してユーザー設定のあいさつ文を作成できます。
*    **[なし]**ユーザーが自動応答の電話番号にコールインのときに、あいさつ文は鳴るなし。
*    **あいさつ文のカスタムを作成します。**このオプションを選択する場合は、(1000 文字) まで読みシステムを設定するテキストを入力します。たとえばのような入力"contoso 社へようこそ。通話はへのご協力ください。"**発信者が**] ボックスにします。
*    **音声ファイルをアップロード**これを選択する場合は、あいさつ文を記録し、(.wav、.mp3 または .wma 形式) でオーディオ ファイルをアップロードします。
***
![番号 2](../images/sfbcallout2.png)<br/>勤務時間中に届く着信はどうなりますかを選択することができます。次のオプションから選択できます。
*    **切断**選択した場合は、業務時間の案内応答を聞く後呼び出し先の人は切断されます。
*    **通話をリダイレクトします。**通話を自動的に送信するために使用できます。
     *    エンタープライズ ボイスを有効になっている、または Office 365 のプランの呼び出しを割り当てられている**電話システムで**ライセンスを使って**社内のユーザー**にします。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択し、着信が直接ボイス メールに転送するのには、この人を設定します。<br/><br/>   
        > [!Note]
        > オンライン ユーザーは、**社内のユーザー**または、ユーザーが内部設置型にホストされている Skype for Business Server 2015 または Lync Server 2013 を使ったします。Lync Server 2010 はサポートされていません。<br/><br/>

     *    通話のキューを使用して**通話キュー**には、呼び出しを設定した電話キューに転送することができます。
     *    サブメニューを含むメニュー オプションの 2 番目のレベルを作成するのには応答自動応答の他の**自動応答**の既存に使用することができます。これらは、入れ子になった自動応答と呼ばれます。
*    **メニュー オプションのプロンプトを再生します。**これらは、再生するように求めるメッセージを設定できるようにも使用できます。
***
![数値 3](../images/sfbcallout3.png)<br/>**メニューのプロンプト**メイン メニューのプロンプトを作成するには、音声合成を使用するか、オーディオ ファイル (.wav、.mp3 または .wma) をアップロードします。メッセージが表示されたら、**発信者が**] ボックスに入力したり、レコード、オーディオ ファイルと、たとえば:"の売り上げ高とまたはキーを押すか 1 とします。サービスは、キーを押すか、2 と言います。カスタマー サポートの場合は、キーを押すか、3 とします。演算子のキーを押すか、0 とします。このメニューをもう一度聞くに星キーを押してまたは繰り返しとします。"**ユーザー設定のメッセージを作成します。**これを選択した場合は、(1000 文字) まで読みシステムを設定するテキストを入力する必要があります。**音声ファイルをアップロード**これを選択した場合は、あいさつ文を記録して (.wav、mp3 または .wma 形式) でオーディオ ファイルをアップロードする必要があります。
***
![番号 4](../images/sfbcallout4.png)<br/>**名前でダイヤル**このオプションを選択する場合は、ディレクトリの検索を使用して、組織内のユーザーを検索する電話の発信元のユーザーこれにより、します。ユーザーとして登録されているか使用できないダイヤル名で**スコープをダイヤルする**] ページでそのオプションを設定を選択することができます。任意のオンラインのユーザーには、**電話システムで**ライセンス、またはすべてのユーザーが内部設置型にホストされている名前によってダイヤルで Skype for Business Server 2015 または Lync Server 2013 では、使いを確認できます。<br/><br/>  **注意:**ユーザーが内部設置型にホストされている名前でダイヤルで Lync 2010 に**到達できない**を使用します。
***

![5](../images/sfbcallout5.png)<br/>**メニュー オプションを編集します。**メニュー オプションの追加またはのキーパッドのキー] ボタンを使用して、削除できます。メニュー オプションを追加するには、キーパッドの対応するキーを押します。使用中のキーを変更する色のオプションの対応する行の下に表示する.メニュー オプションを削除するには、このキーの選択を解除するキーパッド コントロールに対応するキーをクリックします。[キーのマッピング] 行は削除されます。<br/><br/>  **ヒント:**メニューの [画面の指示テキストを更新または再既存] メニューのプロンプトを自動的に行われませんためにのオプションの削除に追加する際、オーディオを個別に記録する必要があります。  <br/><br/>  メニュー オプションを追加し、任意の順序で削除し、キー マッピング連続する必要はありません。たとえば、0、1、および 3 は、2、キーの使用中のオプション] をマップにキーがあるメニューを作成するは、可能なです。<br/><br/> 

    > [!Note] 
    > The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands. <br/><br/>

キーを選択した後に、メニューのオプション] を設定するには、する必要があります。 
- **オプションの名前を入力**これは、最大 64 文字でき。、「カスタマー サービス」または「操作と理由」のような複数の単語を含めることができます。音声認識機能が有効な場合は、名前は自動的に認識され、電話、ユーザーは 3 キーを押すか、「3」とすることや、「カスタマー サービス」キー 3 に対応付けのオプションを選ぶとします。 
- 次の手順では、対応するキーが押されたかどうか、またはオプションを選択する音声認識を使用して送信するが、通話を選択します。を通話を送信できます。 
    - **演算子**演算子は既に設定されている場合が自動的に 0 をキーにマッピングされているも削除したりできる別のキーに再割り当ています。演算子は、いずれかのキーに設定されていない、[音声コマンド「演算子」無効になりますすぎます。 
    - エンタープライズ ボイスを有効になっている、または Office 365 のプランの呼び出しを割り当てられている**電話システムで**ライセンスを使って**社内のユーザー** 。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択し、着信が直接ボイス メールに転送するのには、この人を設定します。<br/><br/> 
    
        > [!Note] 
        > オンライン ユーザーは、**社内のユーザー**または、ユーザーが内部設置型にホストされている Skype for Business Server 2015 または Lync Server 2013 を使ったします。Lync Server 2010 はサポートされていません。<br/><br/>

    - **キューを呼び出す**通話キュー] オプションを使用すると、設定した既存の通話キューに転送する、通話ができます。 
    - **自動応答**サブメニューを含むメニュー オプションの 2 番目のレベルを作成するのには、既存の自動応答を使用することができます。これらは、入れ子になった自動応答と呼ばれます。<br/><br/>
    
        > [!Note]
        > 入れ子になった (または、第 2 レベル) の自動応答の**勤務時間**も使用するように設定されているその他の自動応答の送信、通話を含みます。         
   
### <a name="select-holidays-page"></a>休日のページを選択します。 

各自動応答には、最大で 20 スケジュール休日を追加できます。
  
![自動応答で休日をセットアップします。](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>**祝日を追加します。**[**祝日名**] フィールドで、新しい祝日の名前を入力します。<br/><br/> 祝日名は、64 文字まで可能性がありますで構成され、同じ自動応答の一意である必要があります。たとえば、2 つの祝日を同じの自動応答「感謝祭」という名前を持つことはできません。  
***
![数値 2](../images/sfbcallout2.png)<br/>**休日のあいさつ文**休日のあいさつ文はオプションですし、 **[なし]**に設定できます。この例では、発信者が聞くなしメッセージまたはあいさつ文を選択するオプションのいずれかを処理する前にします。(.Wav、mp3 または .wma 形式で)、音声ファイルをアップロードしたり、音声合成を使用してユーザー設定のあいさつ文を作成できます。
*    **[なし]**ユーザーが自動応答の電話番号にコールインのときに、あいさつ文は鳴るなし。
*    **あいさつ文のカスタムを作成します。**このオプションを選択する場合は、(1000 文字) まで読みシステムを設定するテキストを入力します。たとえば、"おめでとうを入力することがあります。オフィスが現在閉じています。"**発信者が**] ボックスにします。
*    **音声ファイルをアップロード**この場合は、休日のあいさつ文を記録し、(.wav、.mp3 または .wma 形式) でオーディオ ファイルをアップロードします。  
***
![数値 3](../images/sfbcallout3.png)<br/>**あいさつ文の後に、着信どうなりますか?**この休暇中に受信する着信の動作を選択します。次のオプションから選択できます。
*    **切断**休日のあいさつ文を聞く後呼び出し先の人が解除されます。
*    **通話をリダイレクトします。**通話を自動的に送信するために使用できます。
     *    エンタープライズ ボイスを有効になっている、または Office 365 のプランの呼び出しを割り当てられている**電話システムで**ライセンスを使って**社内のユーザー** 。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**] を選択し、[この人の着信が直接ボイス メールに転送するのにを設定します。<br/><br/> 
     
         > [!Note] 
         > オンライン ユーザーは、**社内のユーザー**または、ユーザーが内部設置型にホストされている Skype for Business Server 2015 または Lync Server 2013 を使ったします。Lync Server 2010 はサポートされていません。<br/><br/>

     *    設定した既存の通話キューに通話を転送する**着信キュー**です。
     *    他の**自動応答**] サブメニューを含むメニュー オプションの 2 番目のレベルを作成します。これらは、入れ子になった自動応答と呼ばれます。<br/><br/>
     
         > [!Note]
         > 既定では、休日の期間中に到着したすべての通話とは異なる動作が必要な場合は、リダイレクトを指定する必要がありますので、あいさつ文 (存在する場合) の後に接続または切断に設定されています。

***
![番号 4](../images/sfbcallout4.png)<br/>**休日を開始および終了するとよいですか?**Dd/mm/yyyy 形式で祝日の開始日を入力し、日付の範囲のテーブルにメッセージが表示されたら、[開始時刻、終了日と終了時刻] を選択します。<br/><br/>休暇、最大 10 個の別の日付範囲を指定できます。たとえば、最大 10 年の祝日クリスマスの日付の範囲を追加できます。祝日は、複数の日にまたがることができます。<br/><br/>追加するには、休日の日付の範囲 (たとえば、翌年) に**追加する**には、をクリックしてから入力開始日と終了日、休日の一連の新しい。<br/><br/>入れ子になった休日もサポートされています。たとえば、「祝日改」の 1 つの期間内の複数の祝日をネストする可能性のあります。 
*    **3 年 1 月から 12 月 24日:**"祝日です。現在、オフィスが閉じられています。もう一度開く年 1 月 4 日。"
*    **12 月 25 日:**"クリスマスです。現在、オフィスが閉じられています。もう一度開く年 1 月 4 日。"
*    **1 月 1 日:**"おめでとう現在、オフィスが閉じられています。もう一度開く年 1 月 4 日。"
   
自動応答を保存すると、[**休日**] タブの編集、追加、または休日の設定を変更するを使って休日が表示されます。
  
### <a name="select-dial-scope-page"></a>[ダイヤルのスコープ] ページ

このページには、組織内のどのユーザーになりますダイヤルで利用可能とディレクトリに一覧表示されているときに、組織に通話の相手の名前を設定することができます。
  
![ダイヤル名で検索のスコープをダイヤルしてください。](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>[**含める**] オプションを使用して、2 つのオプションがあります。
*    **オンラインですべてのユーザー**ディレクトリの検索に含まれる、組織のすべてのユーザーは、このオプションを使用します。内部設置型が、ユーザーと同様に、**電話システムで**ライセンスをオンラインすべてのユーザーにホストされている Skype for Business Server 2015 または Lync Server 2013 を持つプランの呼び出し、Office 365 を使ったが表示されます。 
*    **ユーザー設定**このオプションを使用すると、Office 365 のグループ、配布リスト、またはセキュリティ グループを作成すると、組織内を検索することができます、Online ユーザーと Office 365 のグループ、配布リスト、またはのいずれかの**セキュリティ グループにユーザーを追加します。電話システム ライセンス**や社内でホストされている Business Server 2015 または Lync Server 2013 の Skype を使用します。複数の Office 365 グループ、配布リスト、およびセキュリティ グループを追加することができます。<br/><br/> 

    > [!Caution]
    > Lync Server 2010 の展開からオンプレミスのユーザーは、名前でダイヤルを使用して、ディレクトリを検索のユーザーと表示されません。 
***
![数値 2](../images/sfbcallout2.png)<br/>2 つのオプションがある**対象外にする**オプションを使用します。
*    **[なし]**このオプションを使用するには、ディレクトリの検索からオンラインのユーザーが除外なしが示されます。 
*    **ユーザー設定**このオプションを使用している場合、Office 365 のグループ、配布リスト、またはセキュリティ グループを作成すると、組織内を検索することができますこの Office 365 グループ、配布リストに追加されたすべてのユーザーやセキュリティ グループは、ディレクトリの検索から除外されます。複数の Office 365 グループ、配布リスト、およびセキュリティ グループを追加することができます。<br/><br/> 

    > [!Caution]
    > Lync Server 2010 の展開からオンプレミスのユーザーは、名前でダイヤルを使用して、ディレクトリを検索のユーザーと表示されません。          
   
> [!NOTE]
> ディレクトリに一覧表示、ダイヤルの使用時に名前で音声認識を自分の名前を持つ新しいユーザーの最大 36 時間かかる場合があります。 
  
すべての必須フィールドに入力し、通話処理メニューとオプションを設定すると、[**保存**] をクリックします。
  
## <a name="editing-and-testing-auto-attendants"></a>編集して、自動応答をテストします。

自分の自動応答を保存した後、[**自動応答**] ページに表示されます。これは、オプションを選択するオプションを設定した、名前、電話番号、言語、および状態などの一部をすばやく表示することができます。
  
自動応答を変更する場合は、自動応答] を選択し、[アクション] ウィンドウで [**編集**] をクリックします。
  
操作ウィンドウで、[**テスト**] ボタンを使用して、自動応答するテスト電話をかけるも簡単に配置できます。
  
## <a name="want-to-know-more"></a>詳細を知りたいですか。

Windows PowerShell を使ってを作成し、自動応答を設定することもできます。
  
### <a name="auto-attendant-cmdlets"></a>自動応答のコマンドレット

自動応答を管理する必要があるコマンドレットを紹介します。
  
||| 
|---|---|
[新しい-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx)                                                                      | [新しい-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx)                                                              |
| [設定 CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx)                                                                      | [新しい-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx)                                                           |
| [Get CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx)                                                                      | [Get CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [削除 CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx)                                                                   | [新しい-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx)                                                                  |
| [新しい-CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx)                                                                                 | [新しい-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx)                                                              |
| [エクスポート CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [新しい-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx)                                                                                  |
| [新しい-CsOnlineDateTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [新しい-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx)                                                                                   |
| [Get CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/en-us/library/mt796483.aspx)                                                     | [新しい-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx)                                               |
| [Get CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx)                                                     | [インポート CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [新しい-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細

- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連トピック
[ここではされた電話システムで Office 365 での表示](here-s-what-you-get-with-phone-system.md)

[Skype for Business とチームの Microsoft サービスの電話番号を取得します。](getting-service-phone-numbers.md)

[電話会議とプランの呼び出しの国と地域の空き時間情報](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    

