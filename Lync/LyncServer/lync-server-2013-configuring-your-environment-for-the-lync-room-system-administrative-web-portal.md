---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの環境の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f0f415cfeca5b798a1e29ac6ebe09105fbf08b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-22_

Lync Room System (LRS) 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。

<div>


> [!IMPORTANT]  
> サーバーが Kerberos 認証と NTLM 認証の両方で構成されていて、ドメインに参加していないコンピューターで LRS が実行されている場合、Kerberos 認証は失敗し、管理ポータルで LRS の状態は表示されません。 この問題を解決するには、NTLM 認証を使用してサーバーを構成するか、NTLM と DSK 認証の両方 (Kerberos を使用しない)、または LRS コンピューターをドメインに参加させます。



</div>

1.  Lync Server 2013 累積更新プログラムをインストールする: Lync Server トポロジの2013年7月。
    
    更新プログラムを入手したり、アプリに含まれている内容を確認したりするには、「 [Lync Server 2013 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=323959)」を参照してください。

2.  SIP 対応の Active Directory ユーザーを作成します。
    
    LRS 管理 Web ポータルでは、これらの資格情報を使用して Lync Server から情報を照会します。 推奨されるユーザ名は LRSApp です。

3.  LRSSupportAdminGroup という名前の Active Directory セキュリティ グループを作成します。
    
    [グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。このグループに追加される SIP 対応ユーザーは、部屋の一覧を参照したり、ログの収集などの特定のコマンドを実行したりすることができます。

4.  LRSFullAccessAdminGroup という名前の Active Directory セキュリティ グループを作成します。
    
    グループのスコープを持つグループを [グローバル] と [グループ] のセキュリティとして作成します。このグループに追加された SIP 対応ユーザーは、すべての管理ポータル機能を使用することが許可されています。
    
     
    
    ![セキュリティ グループの役割を持つ Admin グループの一覧](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "セキュリティ グループの役割を持つ Admin グループの一覧")  
    
     

5.  LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。
    
    ![LRSSupportAdminGroup プロパティ メンバー ページ](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup プロパティ メンバー ページ")  
    
     

6.  LRSSupport という名前の SIP 対応の Active Directory ユーザーを作成します。 このユーザーを LRSSupportAdminGroup に追加します。
    
    ![LRSSupportAdminGroup プロパティ メンバー ページ](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup プロパティ メンバー ページ")  
    
     

7.  Microsoft ダウンロードセンターで入手可能な Visual Studio 2010 SP1 および Visual Web Developer 2010 SP1 の ASP.NET MVC 4 をインストール[http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)します。

</div>

<span> </span>

</div>

</div>

</div>

