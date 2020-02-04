---
title: 'Lync Server 2013: Microsoft Exchange Server のユニファイド メッセージングと連動させるための Lync Server 2013 の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 985b2d286f65be2353c2ace0d59872f4d0fc47ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Microsoft Exchange Server のユニファイド メッセージングと連動させるための Lync Server 2013 の構成

</div>

<div id="mainSection">

<div id="mainBody">

_**最終更新日:** 2013-04-03_

この手順では、Exchange UM 統合ユーティリティ (OcsUmUtil) が必要です。 このツールは、の Lync Server 2013 サーバーにあります。\\Program Files\\の一般的\\なファイル Microsoft Lync\\Server 2013 サポートフォルダー。

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Exchange UM 統合ユーティリティの実行

Exchange UM 統合ユーティリティは、次の特徴を持つユーザーアカウントから実行されている必要があります。

  - RTCUniversalServerAdmins グループおよび RtcUniversalUserAdmins groups のメンバーシップ (Exchange Server ユニファイドメッセージングの設定を確認するためのアクセス許可を含みます)。

  - ドメイン内のユーザー権利。指定された組織単位 (OU) コンテナーに連絡先オブジェクトを作成します。

Exchange UM 統合ユーティリティを実行すると、次のタスクが実行されます。

  - エンタープライズボイスユーザーが使用する自動応答とサブスクライバーアクセス番号ごとに連絡先オブジェクトを作成します。

  - 各エンタープライズボイスダイヤルプランの名前が、対応するユニファイドメッセージング (UM) ダイヤルプランの電話コンテキストに一致していることを確認します。 この照合が必要なのは、UM ダイヤルプランが Exchange 2010 Service Pack 1 (SP1) よりも*前*のバージョンの exchange で実行されている場合のみです。

> [!IMPORTANT]
> Exchange UM 統合ユーティリティを実行する前に、次の作業を行っていることを確認します。
> <ul>
> <li><p>Exchange 製品のドキュメントで説明されているように、1つ以上の Exchange UM ダイヤルプランを作成します。</p>
> <p>Microsoft Exchange Server 2010 について&quot;は、「AT で&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>UM ダイヤルプランを作成する」をご覧ください。</p>
> <p>Microsoft Exchange Server 2007 Service Pack 1 (SP1) について&quot;は、「ユニファイドメッセージング SIP URI ダイヤルプラン&quot;を<a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>作成する方法」を参照してください。</p></li>
> <li><p>「 <a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013 でダイヤルプランを作成</a>する」の説明に従って、1つまたは複数の lync server のダイヤルプランを作成します。</p></li>
> <ul><li>Microsoft Exchange Server 2010 SP1 より前のバージョンの Exchange を使用している場合は、Lync Server 2013 の [ダイヤルプランの<STRONG>簡易名</STRONG>] フィールドに、対応する Exchange ユニファイドメッセージング (UM) SIP ダイヤルプランの完全修飾ドメイン名 (FQDN) を入力する必要があります。 Microsoft Exchange Server 2010 SP1 または最新の service pack を使用している場合、このダイヤルプランの名前の一致は必要ありません。</li></ul>
> <li>自動応答を作成し、サブスクライバーアクセス番号と自動応答番号の両方が必ず164形式になっていることを確認します。</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Exchange UM 統合ユーティリティを実行するには

1.  フロントエンドサーバーでコマンドプロンプトを開き、「 **cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\サポート**」と入力して、enter キーを押します。

2.  「 **Ocsumutil**」と入力して、enter キーを押します。

3.  [**データの読み込み**] をクリックして、信頼できるすべての Exchange フォレストを検索します。

4.  **Sip ダイヤルプラン**リストで、コンタクトオブジェクトを作成する UM SIP ダイヤルプランを選択し、「**追加**」をクリックします。

5.  [**連絡先**] ボックスで、既定の組織単位をそのまま使用するか、[**参照**] をクリックして**OU 選択**を開始します。 [ **Ou の選択**] ボックスで、ou を選んで [ **OK**] をクリックします。または、ドメイン内のルートまたは他の ou (たとえば、"OU = RTC Special account, dc = 4 thコーヒー, dc = com") に新しい組織単位を作成**するには**、[ **ok**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 選択または作成した OU の識別名 (DN) が [<STRONG>組織単位</STRONG>] ボックスに表示されるようになります。

    
    </div>

6.  [**名前**] ボックスで、既定のダイヤルプラン名をそのまま使うか、作成している連絡先オブジェクトの新しい表示名を入力します。
    
    <div>
    

    > [!NOTE]  
    > たとえば、サブスクライバーアクセスの contact オブジェクトを作成する場合は、"サブスクライバーアクセス" という名前を付けるだけです。

    
    </div>

7.  [ **Sip アドレス**] ボックスに、既定の sip アドレスをそのまま使うか、新しい sip アドレスを入力します。
    
    <div>
    

    > [!NOTE]  
    > 新しい SIP アドレスを入力する場合は、 <STRONG>sip</STRONG>で始める必要があります (つまり、コロンを含む "sip:")。

    
    </div>

8.  [**サーバーまたはプール**] ボックスの一覧で、連絡先オブジェクトを有効にする標準エディションサーバーまたはフロントエンドプールを選択します。
    
    <div>
    

    > [!NOTE]  
    > 可能であれば、選択したプールは、エンタープライズボイスと Exchange UM が有効になっているユーザーが展開する1つのプールである必要があります。

    
    </div>

9.  [**電話番号**] ボックスの一覧で、[**電話番号を入力**するか、 **Exchange UM からこのパイロット番号を使用する**] を選択し、電話番号を入力します。

10. [**連絡先の種類**] ボックスの一覧で、作成する連絡先の種類を選び、[ **OK**] をクリックします。

11. 作成する追加の連絡先オブジェクトについて、手順 1 ~ 10 を繰り返します。
    
    <div>
    

    > [!NOTE]  
    > 自動応答ごとに、少なくとも1つの連絡先を作成する必要があります。 外部アクセスが必要な場合は、サブスクライバーへのアクセスにもサブスクライバーへのアクセスが必要です。また、直接の内側ダイヤル (DID) 番号を指定する必要があります。

    
    </div>

</div>

連絡先オブジェクトが作成されたことを確認するには、[Active Directory ユーザーとコンピューター] を開き、オブジェクトが作成された OU を選択します。 連絡先オブジェクトが詳細ウィンドウに表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

