---
title: "Lync Server 2013: Exchange Server のユニファイド メッセージングと連動する Lync Server 2013 の構成"
TOCTitle: Microsoft Exchange Server のユニファイド メッセージングと連動させるための Lync Server 2013 の構成
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48271293
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Exchange Server のユニファイド メッセージングと連動させるための Lync Server 2013 の構成

 

_**トピックの最終更新日:** 2016-12-08_

このステップを実行するには、Exchange UM 統合ユーティリティ (OcsUmUtil.exe) が必要です。このツールは, ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support フォルダーの Lync Server 2013 サーバーにあります。

## Exchange UM 統合ユーティリティの実行

Exchange UM 統合ユーティリティは、次の特性を持つユーザー アカウントで実行する必要があります。

  - RTCUniversalServerAdmins グループおよび RtcUniversalUserAdmins グループ (Exchange Server ユニファイド メッセージングの設定を読み取るアクセス許可が割り当てられている) に属している。

  - 指定された組織単位 (OU) コンテナーに連絡先オブジェクトを作成するドメイン内ユーザー権限を持つ。

Exchange UM 統合ユーティリティを実行すると、以下のタスクが実行されます。

  - エンタープライズ VoIP ユーザーが使用する各自動応答番号とサブスクライバー アクセス番号の連絡先オブジェクトを作成します。

  - エンタープライズ VoIP の各ダイヤル プランが、対応するユニファイド メッセージング (UM) ダイヤル プランの電話コンテキストと一致するかどうかを検証します。この一致が必要なのは、Exchange 2010 Service Pack 1 (SP1) より前のバージョンの Exchange で UM ダイヤル プランを実行している場合のみです。

> [!IMPORTANT]  
> Exchange UM 統合ユーティリティを実行する前に、以下の作業を確実に実行します。
> <ul><li><p>Exchange の製品ドキュメントの説明のとおりに、1 つ以上の Exchange UM ダイヤル プランを作成します。</p>
> <p>Microsoft Exchange Server 2010 の場合は、「UM ダイヤル プランの作成」(<a href="http://go.microsoft.com/fwlink/?linkid=186177&amp;clcid=0x411  ">http://go.microsoft.com/fwlink/?linkid=186177&amp;clcid=0x411  </a>) を参照してください。</p>
> <p>Microsoft Exchange Server 2007 Service Pack 1 (SP1) の場合は、「ユニファイド メッセージング SIP URI ダイヤル プランを作成する方法」(<a href="http://go.microsoft.com/fwlink/?linkid=185771&amp;clcid=0x411  ">http://go.microsoft.com/fwlink/?linkid=185771&amp;clcid=0x411  </a>) を参照してください。</p></li>
> <li><p>「<a href="https://technet.microsoft.com/ja-jp/library/gg398909(v=ocs.15)">Lync Server 2013 でのダイヤル プランの作成</a>」の説明のとおりに、1 つ以上の対応する Lync Server ダイヤル プランを作成します。</p>
    > [!IMPORTANT]  
    > Microsoft Exchange Server 2010 SP1 より前のバージョンの Exchange を使用している場合、Lync Server 2013 ダイヤル プランの [簡易名] フィールドに、対応する Exchange ユニファイド メッセージング (UM) SIP ダイヤル プランの完全修飾ドメイン名 (FQDN) を入力する必要があります。Microsoft Exchange Server 2010 SP1 または最新のサービス パックを使用している場合は、このダイヤル プラン名の一致は必要ありません。</li>
> <li>自動応答を作成し、サブスクライバー アクセス番号と自動応答番号の両方が E.164 形式であることを確認します。</li></ul>


## Exchange UM 統合ユーティリティを実行するには

1.  フロント エンド サーバーでコマンド プロンプトを開き、「**cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support** 」と入力し、Enter キーを押します。

2.  「**OcsUmUtil.exe** 」と入力し、Enter キーを押します。

3.  \[**データの読み込み**\] をクリックして、信頼できるすべての Exchange フォレストを探します。

4.  \[**SIP ダイヤル プラン**\] ボックスの一覧で、連絡先オブジェクトを作成する UM SIP ダイヤル プランを選択し、\[**追加**\] をクリックします。

5.  \[**連絡先**\] ボックスで、既定の組織単位をそのまま使用するか、または \[**参照**\] をクリックして \[**OU の選択**\] を開始します。 \[**OU の選択**\] ボックスで、OU を選択して \[**OK**\] をクリックするか、または \[**新しい OU の作成**\] をクリックしてルートまたはドメイン内のその他の OU の下に新しい組織単位を作成し、\[**OK**\] をクリックします (たとえば、"OU=RTC Special Accounts,DC=fourthcoffee,DC=com")。
    
    > [!NOTE]  
    > 選択または作成した OU の識別名 (DN) が [<strong>組織単位</strong>] ボックスに表示されます。
	

6.  既定のダイヤル プラン名をそのまま使用するか、作成する連絡先オブジェクトの新しい表示名を \[**名前**\] ボックスに入力します。
    
    > [!NOTE]  
    > たとえば、サブスクライバー アクセス連絡先オブジェクトを作成する場合は、名前を単に「Subscriber Access」とすることもできます。


7.  \[**SIP アドレス**\] ボックスで、既定の SIP アドレスをそのまま使用するか、別の SIP アドレスを入力します。
    
    > [!NOTE]  
    > 別の SIP アドレスを入力する場合は、[<strong>SIP:</strong>](コロンを含む &quot;SIP:&quot;) で始める必要があります。


8.  \[**サーバーまたはプール**\] ボックスの一覧で、連絡先オブジェクトを有効にする対象として Standard Edition サーバーまたは フロント エンド プールを選択します。
    
    > [!NOTE]  
    > プールの場合は、できれば、エンタープライズ VoIP と Exchange UM を有効にしたユーザーを展開するプールと同じプールを選択します。


9.  \[**電話番号**\] ボックスの一覧で、\[**電話番号の入力**\] または \[**Exchange UM からのこのパイロット番号を使用**\] をクリックし、電話番号を入力します。

10. \[**連絡先の種類**\] ボックスの一覧で作成する連絡先の種類を選択し、\[**OK**\] をクリックします。

11. ステップ 1. ～ 10. を繰り返し、必要に応じて、追加の連絡先オブジェクトを作成します。
    
    > [!NOTE]  
    > 自動応答ごとに少なくとも 1 つの連絡先を作成してください。外部アクセスが必要な場合は、サブスクライバー アクセス連絡先が必要であり、DID (Direct Inward Dial) 番号を指定する必要があります。


連絡先オブジェクトが作成されていることを確認するには、Active Directory ユーザーとコンピューターを開き、オブジェクトを作成した OU を選択します。作成したオブジェクトが詳細ウィンドウに表示されます。
