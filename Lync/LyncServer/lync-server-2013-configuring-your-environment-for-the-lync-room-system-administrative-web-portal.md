---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの環境の構成'
TOCTitle: Lync Room System 管理 Web ポータルの環境の構成
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn436325(v=OCS.15)
ms:contentKeyID: 59602750
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Room System 管理 Web ポータルの Lync Server 2013 環境の構成

 

_**トピックの最終更新日:** 2016-12-08_

Lync Room System (LRS) 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。


> [!IMPORTANT]
> サーバーが Kerberos 認証と NTLM 認証の両方で構成されており、LRS がドメインに参加していないコンピューターで実行されている場合、Kerberos 認証は失敗し、管理ポータルで LRS のステータスを見ることはできません。この問題を解決するには、NTLM 認証、または NTLM 認証と TLS-DSK 認証の両方で (Kerberos を使って) サーバーを構成するか、LRS コンピューターをドメインに追加します。



1.  Lync Server 2013 累積更新プログラム (2013 年 7 月) を Lync Server トポロジにインストールする。
    
    更新プログラムの取得やその内容については、「[Lync Server 2013 の更新](http://go.microsoft.com/fwlink/p/?linkid=323959)」を参照してください。

2.  SIP 対応の Active Directory ユーザーを作成する。
    
    LRS 管理 Web ポータルでは、これらの資格情報を使用して、Lync Server から情報をクエリします。推奨されるユーザー名は LRSApp です。

3.  LRSSupportAdminGroup という名前の Active Directory セキュリティ グループを作成する。
    
    \[グループのスコープ\] が \[グローバル\]、\[グループの種類\] が \[セキュリティ\] のグループを作成します。このグループに追加される SIP 対応ユーザーは、部屋の一覧を参照したり、ログの収集などの特定のコマンドを実行したりすることができます。

4.  LRSFullAccessAdminGroup という名前の Active Directory セキュリティ グループを作成する。
    
    \[グループのスコープ\] が \[グローバル\]、\[グループの種類\] が \[セキュリティ\] のグループを作成します。このグループに追加される SIP 対応ユーザーは、管理ポータルのすべての機能を使用できます。
    
     
    
    ![セキュリティ グループの役割を持つ Admin グループの一覧](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "セキュリティ グループの役割を持つ Admin グループの一覧")  
    
     

5.  LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加する。
    
    ![LRSSupportAdminGroup プロパティ メンバー ページ](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup プロパティ メンバー ページ")  
    
     

6.  LRSSupport という名前の SIP 対応の Active Directory ユーザーを作成します。このユーザーを LRSSupportAdminGroup に追加します。
    
    ![LRSSupportAdminGroup プロパティ メンバー ページ](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup プロパティ メンバー ページ")  
    
     

7.  Visual Studio 2010 SP1 および Visual Web Developer 2010 SP1 用に、ASP.NET MVC 4 をインストールする。これは、Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)) で入手できます。

