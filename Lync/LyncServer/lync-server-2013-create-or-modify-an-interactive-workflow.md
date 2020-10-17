---
title: 'Lync Server 2013: 対話ワークフローを作成または変更する'
description: 'Lync Server 2013: 対話ワークフローを作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 470a073322c48c351dbfdfb24ce376731b3e7512
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546993"
---
# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>Lync Server 2013 での対話ワークフローの作成または変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-09-11_

対話ワークフローを作成または変更するには、以下のいずれかの手順を使用します。

<div>


> [!NOTE]  
> Lync Server 管理シェルまたは応答グループ構成ツールを使用して、対話型ワークフローを作成および変更できます。 [Lync Server コントロールパネル] から応答グループ構成ツールにアクセスするか、次の URL を入力して web ブラウザーから直接 web ページを開くことによって、 <STRONG>Https://</STRONG> &lt; webpoolfqdn &gt; <STRONG>/RgsConfig</STRONG>にアクセスできます。



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>応答グループ構成ツールを使用して対話ワークフローを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。

4.  [**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。

5.  [**サービスの選択**] 検索フィールドに、作成または変更するワークフローをホストする **ApplicationServer** サービスの名前または名前の一部を入力します。 表示されたサービスの一覧で、目的のサービスをクリックし、[**OK**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 応答グループ構成ツールが開きます。 次の URL を入力して、web ブラウザーから応答グループ構成ツールを直接開くこともできます。 <STRONG>Https://</STRONG> &lt; webpoolfqdn &gt; <STRONG>/RgsConfig</STRONG>。

    
    </div>

6.  次のいずれかの操作を行います。
    
      - [**新規ワークフローの作成**] の [**対話型**] の横にある [**作成**] をクリックします。
    
      - [**既存ワークフローの管理**] で変更するワークフローを見つけて、[**アクション**] の [**編集**] をクリックします。

7.  ユーザーがワークフローへの通話を開始できる状態ではない場合は、[**ワークフローのアクティブ化**] チェック ボックスをオフにします。
    
    <div>
    

    > [!NOTE]  
    > 管理ワークフローを作成する場合は、[<STRONG>ワークフローのアクティブ化</STRONG>] を選択する必要があります。アクティブな管理ワークフローを保存した後、そのワークフローを変更したり、非アクティブ化したりできます。

    
    </div>

8.  フェデレーション ユーザーにグループへの通話を許可するには、[**フェデレーションを有効にする**] チェック ボックスをオンにします。 また、フェデレーション用に構成された応答グループアプリケーションに適用される外部アクセスポリシーも必要です。
    
    <div>
    

    > [!NOTE]  
    > グローバル外部アクセスポリシーは、応答グループアプリケーションに適用されます。 Lync Server コントロールパネルを使用するか、 <STRONG>get-csexternalaccesspolicy</STRONG> コマンドレットを使用して EnableOutsideAccess パラメーターを True に設定することによって、応答グループフェデレーションのグローバルポリシーを構成できます。 グローバル ポリシー設定は、サイトやユーザー ポリシーに割り当てられていない限り、すべてのユーザーに適用されることに注意してください。 そのため、応答グループ向けにこの設定を変更する前に、フェデレーション設定が組織の要件を満たしていることを確認してください。 ポリシーをユーザーに適用する方法の詳細については、「 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 の外部アクセスポリシーの管理</A>」を参照してください。 フェデレーション設定の詳細については、「 <STRONG>get-csexternalaccesspolicy</STRONG> 」の「Lync Server Management Shell」のドキュメントを参照してください。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync Online でホストされているユーザーは、オンプレミスの展開でホストされている応答グループに電話をかけることはできません。 これは、ハイブリッド展開とオンプレミス展開が Lync Online 展開とフェデレーションされている場合の両方で当てはまります。

    
    </div>

9.  通話中、エージェントの ID を非表示にするには、[**エージェントの匿名性を有効にする**] チェック ボックスをオンにします。
    
    <div>
    

    > [!NOTE]  
    > 匿名呼び出しは、インスタントメッセージング (IM) またはビデオで開始することはできません。ただし、エージェントまたは発信者は、呼び出しが確立された後に IM とビデオを追加できます。 匿名エージェントは、通話を保留にしたり、通話を転送したり (ブラインドおよび提案転送の両方) したり、通話をパークおよび取得したりすることもできます。 匿名呼び出しでは、会議、アプリケーション共有とデスクトップ共有、ファイル転送、ホワイトボードとデータコラボレーション、通話記録はサポートされません。 Lync VDI プラグインを使用するエージェントは、匿名で着信呼び出しを受信できますが、匿名で発信呼び出しを行うことはできません。

    
    </div>

10. [**通話を受けるグループのアドレスを入力します**] に、ワークフローへの通話に応答するグループのプライマリ SIP Uniform Resource Identifier (URI) アドレスを入力します。

11. [**表示名**] に、ワークフローを表示する名前を入力します (入力例: Sales IVR Response Group)。
    
    <div>
    

    > [!NOTE]  
    > [ &lt; 表示名] に "" または "" 文字を含めないでください &gt; 。 次の表示名は、予約されているため、使用しないでください。 RG プレゼンス監視またはアナウンスサービス。

    
    </div>

12. [**電話番号**] に、応答グループの回線 URI を入力します (入力例 +14255550165)。

13. [**表示番号**] に、応答グループを表示する番号を入力します (入力例 +1 (425) 555-0165)。

14. オプション[ **説明**] に、Lync クライアントの連絡先カードに表示するワークフローの説明を入力します。

15. このワークフローを応答グループのマネージャーが管理する場合は、[**ワークフローの種類**] で [**管理**] を選択します。 ワークフローを応答グループのマネージャーに割り当てるには、次の操作を実行します。
    
    1.  このワークフローのマネージャーの SIP URI を入力して、[**追加**] をクリックします。
    
    2.  ワークフローに追加するマネージャーの SIP URI を入力して、[**追加**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > 応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。

    
    </div>

16. [**ステップ 2 言語の選択**] で、音声認識と音声合成で使用する言語をクリックします。

17. 開始メッセージを構成する場合は、[**ステップ 3 開始メッセージの構成**] で [**開始メッセージを再生する**] チェック ボックスをオンにして、次のいずれかの操作を行います。
    
      - 発信者用の音声に変換される開始メッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスに開始メッセージを入力します。
        
        <div>
        

        > [!NOTE]  
        > 入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。

        
        </div>
    
      - 開始メッセージに Wave または Windows Media オーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するオーディオ ファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。
        
        <div>
        

        > [!NOTE]  
        > ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。 サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。

        
        </div>

18. [**ステップ 4 営業時間の指定**] の [**タイム ゾーン**] ボックスで、ワークフローのタイム ゾーンをクリックします。
    
    <div>
    

    > [!NOTE]  
    > このタイム ゾーンは、ワークフローの発信者とエージェントの所在地のタイム ゾーンです。 これを使用して、始業時間と終業時間が計算されます。 たとえば、北アメリカ東部標準時を使用するようにワークフローが構成されており、ワークフローで始業が午前 7:00、終業が11:00:00 にスケジュールされている場合は、東部標準時の 7:00 と 23:00 がそれぞれ始業時刻と終業時刻になります  (時間は 24 時間表記で入力する必要があります)。

    
    </div>

19. 次のいずれかの操作を実行して、使用する営業時間スケジュールの種類を選択します。
    
      - 事前に定義した営業時間スケジュールを使用するには、[**事前設定したスケジュールを使用する**] をクリックして、ドロップダウン リストから使用するスケジュールを選択します。
        
        <div>
        

        > [!NOTE]  
        > このオプションを選択できるようにするには、あらかじめ少なくとも 1 つの事前設定スケジュールを定義しておく必要があります。 <STRONG>New-CSRgsHoursOfBusiness</STRONG> コマンドレットを使用して事前設定スケジュールを定義します。 詳細については、「 <A href="lync-server-2013-optional-define-response-group-business-hours.md">Lync Server 2013 で応答グループの営業時間を定義する (オプション)</A>」を参照してください。 事前設定したスケジュールを選択すると、応答グループの対応日時で、[<STRONG>曜日</STRONG>]、[<STRONG>始業</STRONG>]、[<STRONG>終業</STRONG>] が自動的に設定されます。

        
        </div>
    
      - このワークフローのみに適用するカスタム スケジュールを使用するには、[**カスタム スケジュールを使用する**] をクリックします。

20. このワークフロー用のカスタム スケジュールを作成する場合は、応答グループが対応可能な曜日のチェック ボックスをオンにします。

21. カスタム スケジュールを作成する場合は、応答グループが対応可能な [**始業**] 時間と [**終業**] 時間を入力します。
    
    <div>
    

    > [!NOTE]  
    > [<STRONG>始業</STRONG>] 時間と [<STRONG>終業</STRONG>] 時間は 24 時間表記で入力する必要があります。 たとえば、職場の営業時間が営業日の 9 ～ 5 時までで、昼休みのために正午にオフィスを一度閉める場合、営業時間は [<STRONG>始業</STRONG>] 9:00、[<STRONG>終業</STRONG>] 12:00、[<STRONG>始業</STRONG>] 13:00、[<STRONG>終業</STRONG>] 17:00 として指定します。

    
    </div>

22. 営業時間外にメッセージを再生するには、[**応答グループの営業時間外にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。
    
      - 発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。
        
        <div>
        

        > [!NOTE]  
        > 入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。

        
        </div>
    
      - メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。
        
        <div>
        

        > [!NOTE]  
        > ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。 サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。

        
        </div>

23. メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。
    
      - 通話を終了するには、[**終話**] をクリックします。
    
      - 通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。 ボイスメールアドレスの形式は次のようになり \<username\> @ \<domainname\> ます (たとえば、bob@contoso.com)。
    
      - 通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。 ユーザーアドレスの形式は \<username\> @ \<domainname\> です。
    
      - 通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。 電話番号の形式は次のようになり \<number\> @ \<domainname\> ます (たとえば、+ 14255550121@contoso.com)。 発信者は、ドメイン名を使用して適切な宛先にルーティングされます。

24. [**ステップ 5 休日の指定**] で、応答グループが営業しない日を定義する、1 つまたは複数の休日セットのチェック ボックスをオンにします。
    
    <div>
    

    > [!NOTE]  
    > ワークフローを構成する前に、休日および休日セットを定義する必要があります。 休日および休日セットを定義するには、<STRONG>New-CsRgsHoliday</STRONG> コマンドレットおよび <STRONG>New-CsRgsHolidaySet</STRONG> コマンドレットを使用します。 詳細については、「 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">Lync Server 2013 で応答グループの休日セットを定義する (オプション)</A>」を参照してください。

    
    </div>

25. 休日にメッセージを再生するには、[**休日にメッセージを再生する**] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。
    
      - 発信者用に音声に変換されるメッセージをテキストとして入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスにメッセージを入力します。
        
        <div>
        

        > [!NOTE]  
        > 入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。

        
        </div>
    
      - メッセージにオーディオ ファイルの録音を使用するには、[**録音を選択する**] をクリックします。新しいオーディオ ファイルをアップロードする場合は、[**録音**] リンクをクリックしてください。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。
        
        <div>
        

        > [!NOTE]  
        > ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。 サポートされているオーディオファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。

        
        </div>

26. メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。
    
      - 通話を終了するには、[**終話**] をクリックします。
    
      - 通話をボイス メールに転送するには、[**ボイス メールに転送**] をクリックして、ボイス メール アドレスを入力します。 ボイスメールアドレスの形式は次のようになり \<username\> @ \<domainname\> ます (たとえば、bob@contoso.com)。
    
      - 通話を別のユーザーに転送するには、[**SIP URI に転送**] をクリックして、ユーザー アドレスを入力します。 ユーザーアドレスの形式は \<username\> @ \<domainname\> です。
    
      - 通話を別の電話番号に転送するには、[**電話番号に転送**] をクリックして、電話番号を入力します。 電話番号の形式は次のようになり \<number\> @ \<domainname\> ます (たとえば、+ 14255550121@contoso.com)。 発信者は、ドメイン名を使用して適切な宛先にルーティングされます。

27. [**ステップ 6 保留音の構成**] で、次のいずれかの操作を実行して、発信者がエージェントの応答を待機しているときの保留音を選択します。
    
      - 既定の保留音の録音を使用する場合は、[**既定値を使用する**] をクリックします。
    
      - 保留音にオーディオ ファイルの録音を使用するには、[**音楽ファイルを選択する**] をクリックします。 新しいオーディオ ファイルをアップロードする場合は、[**音楽ファイル**] リンクをクリックします。新しいブラウザー ウィンドウで [**参照**] をクリックし、使用するファイルを選択して、[**開く**] をクリックします。[**アップロード**] をクリックしてオーディオ ファイルを読み込みます。
        
        <div>
        

        > [!NOTE]  
        > ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。 サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。

        
        </div>

28. [**ステップ 7 対話型音声応答の構成**] の [**ユーザーには、次のテキストまたは録音メッセージを再生します**] という見出しの下で、次のように発信者に対する質問を指定します。
    
      - 質問をテキスト形式で入力するには、[**音声合成を使用する**] をクリックして、テキスト ボックスに質問を入力します。
        
        <div>
        

        > [!NOTE]  
        > 入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > "#" 記号は、音声合成エンジンによって "番号" という語に変換されます。 # キーを示す必要がある場合は、記号ではなく、キーの名前を質問に使用してください。 たとえば、「営業部門をご希望の場合は、シャープを押してください」とします。

        
        </div>
    
      - 質問を含む録音済みのオーディオ ファイルを使用する場合は、[**録音を選択する**] をクリックし、[**録音**] リンクをクリックしてファイルをアップロードします。 新しいブラウザー ウィンドウで [**参照**] をクリックし、オーディオ ファイルを選択して、[**開く**] をクリックします。 [**アップロード**] をクリックしてファイルを読み込んでから、必要な場合はテキスト ボックスに質問を入力します (これにより、質問と発信者の応答が応答エージェントに転送されます)。
        
        <div>
        

        > [!NOTE]  
        > ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。 サポートされているファイル形式の詳細については、「 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</A>」を参照してください。

        
        </div>

29. [**応答 1**] で次の操作を実行して、質問に対する 1 つ目の回答を指定します。
    
    <div>
    

    > [!IMPORTANT]  
    > いずれの音声応答にも引用符 (") を使用しないでください。 引用符は IVR が失敗する原因になります。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 発信者が音声、英数字のキーパッド入力、または両方を使用して回答できるようにすることもできます。

    
    </div>
    
      - 発信者が音声で応答できるようにする場合は、[**音声応答の入力**] に応答を入力します。
    
      - 発信者がキーパッドのキー入力で応答できるようにする場合は、[**数字**] で、目的のキーパッドの数字をクリックします。

30. 次のように、発信者をキューにルーティングするか、もう 1 つ質問するかを指定します。
    
      - 発信者をキューにルーティングするには [**キューに送る**] をクリックし、[**キューの選択**] で使用するキューをクリックします。
    
      - もう 1 つ質問をするには、[**もう 1 つ質問する**] をクリックしてから、[**音声合成を使用する**] をクリックして質問を入力するか、[**録音を選択する**] をクリックします。 このセクションにある応答グループを使用して、追加の質問に対する最大 4 つの応答と、各応答で使用するキューを指定します。 3 番目または 4 番目の応答を指定するには、[**応答 3**] チェック ボックスまたは [**応答 4**] チェック ボックスをオンにします。

31. 手順 28 と 29 を繰り返して応答と各応答に対するアクションを指定し、元の質問に対する回答を最大 3 つ追加します。 3 番目または 4 番目の回答を指定するには、[**応答 3**] チェック ボックスまたは [**応答 4**] チェック ボックスをオンにします。

32. [**展開**] をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>Windows PowerShell を使用して対話ワークフローを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  応答グループ サービスのサービス名を取得して変数に割り当てます。コマンド ラインで、次のコマンドを実行します。
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  対話ワークフローには、2 つ以上のキューと 2 つ以上のエージェント グループが必要です。まず、エージェント グループを作成します。次のコマンドを実行します。
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  キューを作成します。次のコマンドを実行します。
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  応答グループ プロンプトを作成します。次のコマンドを実行します。
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  次に、プロンプトの後に実行するアクションを作成します。次のコマンドを実行します。
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  最初の応答グループ回答を作成します。次のコマンドを実行します。
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  2 番目のプロンプト、通話アクション、および回答を作成します。まず、プロンプトを作成します。次のコマンドを実行します。
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. 2 番目の通話アクションを作成します。次のコマンドを実行します。
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. 2 番目の応答グループ回答を作成します。次のコマンドを実行します。
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. 最上位のプロンプトを作成します。次のコマンドを実行します。
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. 最上位の質問を作成します。次のコマンドを実行します。
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. ここで、ワークフローを作成します。次のコマンドを実行します。
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > 応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

