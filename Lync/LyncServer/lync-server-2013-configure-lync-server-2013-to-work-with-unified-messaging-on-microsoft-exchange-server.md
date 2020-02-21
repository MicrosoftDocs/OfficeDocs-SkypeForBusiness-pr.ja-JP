---
title: 'Lync Server 2013: Microsoft Exchange Server でユニファイドメッセージングを使用するように Lync Server 2013 を構成する'
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
ms.openlocfilehash: d0dc8bc60f87b981a18f351df8ddd163d1b080be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Microsoft Exchange Server でユニファイドメッセージングを使用するように Lync Server 2013 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

_**トピックの最終更新日:** 2013-04-03_

このステップを実行するには、Exchange UM 統合ユーティリティ (OcsUmUtil.exe) が必要です。 このツールは、の Lync Server 2013 サーバーにあります。\\Program Files\\Common Files\\Microsoft Lync Server 2013\\サポートフォルダ。

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Exchange UM 統合ユーティリティの実行

Exchange UM 統合ユーティリティは、次の特性を持つユーザー アカウントで実行する必要があります。

  - RTCUniversalServerAdmins グループおよび RtcUniversalUserAdmins グループ (Exchange Server ユニファイド メッセージングの設定を読み取るアクセス許可が割り当てられている) に属している。

  - 指定された組織単位 (OU) コンテナーに連絡先オブジェクトを作成するための、ドメイン内のユーザー権限。

Exchange UM 統合ユーティリティを実行すると、以下のタスクが実行されます。

  - エンタープライズ VoIP ユーザーが使用する各自動応答番号とサブスクライバー アクセス番号の連絡先オブジェクトを作成します。

  - 各エンタープライズ Voip ダイヤルプランの名前が、対応するユニファイドメッセージング (UM) ダイヤルプランの電話のコンテキストに一致することを確認します。 この一致は、UM ダイヤルプランが Exchange 2010 Service Pack 1 (SP1) より*前*のバージョンの exchange 上で実行されている場合にのみ必要です。

> [!IMPORTANT]
> Exchange UM 統合ユーティリティを実行する前に、次の操作が完了していることを確認してください。
> <ul>
> <li><p>Exchange 製品のドキュメントで説明されているように、1つ以上の Exchange UM ダイヤルプランを作成します。</p>
> <p>Microsoft Exchange Server 2010 について&quot;は、「UM ダイヤル&quot;プラン<a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>を作成する」を参照してください。</p>
> <p>Microsoft Exchange Server 2007 Service Pack 1 (SP1) について&quot;は、「How to Create a ユニファイドメッセージング&quot; SIP <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>URI ダイヤルプラン」を参照してください。</p></li>
> <li><p>「 <a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013 でダイヤルプランを作成</a>する」の説明に従って、1つ以上の対応する lync server ダイヤルプランを作成します。</p></li>
> <ul><li>Microsoft Exchange Server 2010 SP1 より前のバージョンの Exchange を使用している場合は、対応する Exchange ユニファイドメッセージング (UM) SIP ダイヤルプランの完全修飾ドメイン名 (FQDN) を Lync Server 2013 ダイヤルプランの [<STRONG>簡易名</STRONG>] フィールドに入力する必要があります。 Microsoft Exchange Server 2010 SP1 または最新の service pack を使用している場合は、このダイヤルプラン名の一致は必要ありません。</li></ul>
> <li>自動応答を作成し、サブスクライバー アクセス番号と自動応答番号の両方が E.164 形式であることを確認します。</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Exchange UM 統合ユーティリティを実行するには

1.  フロントエンドサーバーで、コマンドプロンプトを開き、「 **cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\サポート**」と入力し、enter キーを押します。

2.  「**OcsUmUtil.exe**」と入力し、Enter キーを押します。

3.  **[データの読み込み]** をクリックして、信頼できるすべての Exchange フォレストを探します。

4.  **[SIP ダイヤル プラン]** ボックスの一覧で、連絡先オブジェクトを作成する UM SIP ダイヤル プランを選択し、**[追加]** をクリックします。

5.  **[連絡先]** ボックスで、既定の組織単位をそのまま使用するか、または **[参照]** をクリックして **[OU の選択]** を開始します。 **[OU の選択]** ボックスで、OU を選択して **[OK]** をクリックするか、または **[新しい OU の作成]** をクリックしてルートまたはドメイン内のその他の OU の下に新しい組織単位を作成し、**[OK]** をクリックします (たとえば、"OU=RTC Special Accounts,DC=fourthcoffee,DC=com")。
    
    <div>
    

    > [!NOTE]  
    > 選択または作成した OU の識別名 (DN) が <STRONG>[組織単位]</STRONG> ボックスに表示されます。

    
    </div>

6.  既定のダイヤル プラン名をそのまま使用するか、作成する連絡先オブジェクトの新しい表示名を **[名前]** ボックスに入力します。
    
    <div>
    

    > [!NOTE]  
    > たとえば、サブスクライバー アクセス連絡先オブジェクトを作成する場合は、名前を単に「Subscriber Access」とすることもできます。

    
    </div>

7.  **[SIP アドレス]** ボックスで、既定の SIP アドレスをそのまま使用するか、別の SIP アドレスを入力します。
    
    <div>
    

    > [!NOTE]  
    > 別の SIP アドレスを入力する場合は、<STRONG>[SIP:]</STRONG>(コロンを含む "SIP:") で始める必要があります。

    
    </div>

8.  [**サーバーまたはプール**] の一覧で、連絡先オブジェクトを有効にする Standard Edition サーバーまたはフロントエンドプールを選択します。
    
    <div>
    

    > [!NOTE]  
    > プールの場合は、できれば、エンタープライズ VoIP と Exchange UM を有効にしたユーザーを展開するプールを選択します。

    
    </div>

9.  **[電話番号]** ボックスの一覧で、**[電話番号の入力]** または **[Exchange UM からのこのパイロット番号を使用]** をクリックし、電話番号を入力します。

10. **[連絡先の種類]** ボックスの一覧で作成する連絡先の種類を選択し、**[OK]** をクリックします。

11. ステップ 1. ～ 10. を繰り返し、必要に応じて、追加の連絡先オブジェクトを作成します。
    
    <div>
    

    > [!NOTE]  
    > 自動応答ごとに少なくとも 1 つの連絡先を作成してください。外部アクセスが必要な場合は、サブスクライバー アクセス連絡先が必要であり、DID (Direct Inward Dial) 番号を指定する必要があります。

    
    </div>

</div>

連絡先オブジェクトが作成されていることを確認するには、Active Directory ユーザーとコンピューターを開き、オブジェクトを作成した OU を選択します。作成したオブジェクトが詳細ウィンドウに表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

