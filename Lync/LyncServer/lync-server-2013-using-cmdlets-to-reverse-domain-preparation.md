---
title: 'Lync Server 2013: コマンドレットを使用してドメインの準備を元に戻す'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac26e17ad9e0ab13529da438bc2e12bec210808d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Lync Server 2013 のコマンドレットを使用してドメインの準備を元に戻す

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

**Disable-CsAdDomain** コマンドレットを使用して、ドメインの準備ステップを元に戻します。

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>コマンドレットを使用してドメインの準備を元に戻すには

1.  Domain Admins グループのメンバーとしてドメイン内の任意のサーバーにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  実行
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    次に例を示します。
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Force パラメーターが指定されている場合は、ドメイン内の1つ以上のフロントエンドサーバーまたは音声ビデオ会議サーバーがアクティブになっていても、ドメインの準備がロールバックされます。 Force パラメーターが指定されていない場合は、ドメイン内のフロントエンドサーバーまたは音声ビデオ会議サーバーがアクティブ化されていると、ドメインの準備のロールバックが終了します。
    
    <div>
    

    > [!NOTE]  
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。 設定をシステム コンテナーに保存する (構成コンテナーにグローバル設定を移行していないアップグレードの展開で一般的) 場合、使用する Active Directory フォレストのルートに 1 つのドメイン コントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、コマンドレットは、設定が構成コンテナーに格納されていると見なし、AD&nbsp;DS の任意のドメインコントローラーを参照します。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のドメインの準備を実行する](lync-server-2013-running-domain-preparation.md)  


[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

