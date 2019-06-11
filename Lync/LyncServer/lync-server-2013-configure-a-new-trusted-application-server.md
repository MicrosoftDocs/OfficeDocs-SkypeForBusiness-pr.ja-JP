---
title: 'Lync Server 2013: 新しい信頼できるアプリケーションサーバーを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Lync Server 2013 で新しい信頼できるアプリケーションサーバーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

信頼されたアプリケーションは、microsoft Lync Server 2013 によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 コア SDK に基づくアプリケーションです。 UCMA アプリケーションの詳細については、の「ユニファイドコミュニケーションマネージ API 3.0 Core [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)SDK ドキュメント」を参照してください。

Microsoft Outlook Web Access (OWA) および Lync Server 2013 の構成の詳細については、Microsoft Exchange Server 2013 ドキュメントの「Outlook Web App および Lync Server 2010 の統合を構成する」を参照してください。

トポロジの公開、有効化、または無効化を成功させるには、サーバーの役割を追加または削除するときに、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。 また、サーバーの役割を追加するための適切な管理者権限と権限を委任することもできます。 詳細については、展開ドキュメントの「 [Lync Server 2013 でのセットアップ権限の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。 その他の構成変更については、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

<div>

## <a name="to-configure-a-trusted-application-server"></a>信頼できるアプリケーションサーバーを構成するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

3.  [**既存の展開からトポロジをダウンロード**] を選び、[ **OK**] をクリックします。

4.  [名前を付け**てトポロジを保存**] ダイアログボックスで、使用するトポロジビルダーファイルをクリックし、[**保存**] をクリックします。

5.  左側のウィンドウで、[**信頼されたアプリケーションサーバー**] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。

6.  信頼されているアプリケーションプールの**プール FQDN**を入力し、それが単一サーバーか複数サーバーかを選択して、[**次へ**] をクリックします。

7.  **[次ホップの選択**] ページで、一覧から Lync Server 2013 フロントエンドプールを選びます。

8.  [**完了**] をクリックします。

9.  トップノードの**Lync Server 2013**を選択し、[**操作**] メニューの [**トポロジの公開**] をクリックします。
    
    **信頼できるアプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられている必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

