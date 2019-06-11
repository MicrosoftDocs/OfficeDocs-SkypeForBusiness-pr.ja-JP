---
title: 'Lync Server 2013: プール展開のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a1dc68b8dbe6285cdf4b7e9c21c873caaf730d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Lync Server 2013 でのプール展開のテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-09-25_

次の手順では、フロントエンドプールの展開をテストする方法について説明します。

<div>

## <a name="to-test-the-pool-deployment"></a>プールの展開をテストするには

1.  Active Directory コンピューターとユーザーを使用して、Lync Server 2013 の展開 (Lync Server 2013 コントロールパネルがインストールされている場合) の管理者ロールの Active Directory ユーザーオブジェクトを**csadministrator**グループに追加します。
    
    <div>
    

    > [!IMPORTANT]  
    > 適切なユーザーとグループを CsAdministors グループに追加していない場合は、Lync Server コントロールパネルを開くとエラーが発生します。これは、"権限がありません。ロールベースのアクセス制御 (RBAC) 承認エラーによりアクセスが拒否されました。" というメッセージが表示されます。

    
    </div>

2.  ユーザーオブジェクトが現在ログオンしている場合は、ログオフしてから再びログオンして、新しいグループの割り当てを登録します。
    
    <div>
    

    > [!NOTE]  
    > ユーザーアカウントを、Lync Server 2013 を実行しているサーバーのローカル管理者にすることはできません。

    
    </div>

3.  管理者アカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。

4.  Lync Server コントロールパネルを起動し、メッセージが表示されたら、資格情報を入力します。 Lync Server コントロールパネルに展開情報が表示されます。

5.  左側のナビゲーションバーで、[**トポロジ**] をクリックし、[サービスの状態] に緑色の矢印が表示されていることを確認し、[レプリケーションの状態] に緑色のチェックマークが表示されることを確認します。

6.  左側のナビゲーションバーで [**ユーザー**] をクリックし、[**ユーザーの有効化**] をクリックします。

7.  [**新しい Lync Server ユーザー** ] ページで、[**追加**] をクリックします。

8.  検索するオブジェクトの検索パラメーターを定義するには、[ **Active Directory から選択**] ページで [**検索**] を選択し、必要に応じて [**フィルターの追加**] をクリックします。 **Ldap 検索**を選択し、返されるオブジェクトをフィルター処理または制限するための ldap 式を入力することもできます。 検索オプションを決定したら、clink**検索**] を選びます。

9.  [検索結果] ウィンドウで、この検索セッションのオブジェクトをすべて選択し、[ **OK]** をクリックします。

10. [**新しい Lync Server ユーザー** ] ページで、選択したオブジェクトが**ユーザー**に表示されます。 [**プールへのユーザーの割り当て**] ボックスの一覧で、オブジェクトのホームにするサーバーを選びます。
    
    次に、オブジェクトを構成するためのいくつかのオプションを示します。
    
      - **ユーザーの SIP URI を生成する**
    
      - **テレフォニー**
    
      - **行の URI**
    
      - **会議ポリシー**
    
      - **クライアントのバージョンポリシー**
    
      - **PIN ポリシー**
    
      - **外部アクセスポリシー**
    
      - **アーカイブポリシー**
    
      - **場所のポリシー**
    
      - **クライアントポリシー**
    
    基本的な機能をテストするために、[**ユーザーの SIP URI の生成**に使用するオプションを選択してください (構成のその他のオプションでは既定の設定が使用されます)] を選び、[**有効に**する] をクリックします。

11. 概要ページが表示され、[**有効**] 列にチェックマークが表示され、オブジェクトが使用できるようになったことを示します。 **SIP アドレス**列には、ユーザーのサインイン構成に必要なアドレスが表示されます。

12. 1人のユーザーをドメインに参加しているコンピューターにログオンし、別のユーザーをドメイン内の別のコンピューターにログオンします。

13. 2台の各クライアントコンピューターに Lync 2013 をインストールし、両方のユーザーが Lync Server 2013 にサインインして、互いにインスタントメッセージを送信できることを確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

