---
title: 'Lync Server 2013: 新しい信頼されたアプリケーションサーバーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e370c229442d90d6e962f0d73efbf4b94038926a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Lync Server 2013 で新しい信頼されたアプリケーションサーバーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

信頼されたアプリケーションは、microsoft Lync Server 2013 によって信頼されている Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 コア SDK に基づくアプリケーションです。 UCMA アプリケーションの詳細については、「ユニファイドコミュニケーション Managed API 3.0 Core SDK [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)Documentation」を参照してください。

Microsoft Outlook Web Access (OWA) および Lync Server 2013 の構成の詳細については、Microsoft Exchange Server 2013 のドキュメントの「Outlook Web App および Lync Server 2010 の統合を構成する」を参照してください。

サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。 サーバーの役割を追加するための、適切な管理者アクセス許可および権限を委任することもできます。 詳細については、「展開」のドキュメントの「 [Delegate setup permissions In Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) 」を参照してください。 他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

<div>

## <a name="to-configure-a-trusted-application-server"></a>信頼されたアプリケーションサーバーを構成するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

3.  [**既存の展開からトポロジをダウンロードする**] を選択し、[**OK**] をクリックします。

4.  [**トポロジを名前を付けて保存**] ダイアログボックスで、使用するトポロジビルダーファイルをクリックし、[**保存**] をクリックします。

5.  左側のウィンドウで、[**信頼されたアプリケーションサーバー**] を右クリックし、[**新しい信頼済みアプリケーションプール**] をクリックします。

6.  信頼済みアプリケーション プールの [**プールの FQDN**] を入力してから、単一サーバーにするか複数サーバーにするかを選択し、[**次へ**] をクリックします。

7.  [**次ホップの選択**] ページで、リストから Lync Server 2013 フロントエンドプールを選択します。

8.  [**完了**] をクリックします。

9.  トップノードの [ **Lync Server 2013**] を選択し、[**操作**] メニューの [**トポロジの公開**] をクリックします。
    
    信頼された**アプリケーションプール**が正常に作成され、適切なフロントエンドプールに関連付けられている必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

