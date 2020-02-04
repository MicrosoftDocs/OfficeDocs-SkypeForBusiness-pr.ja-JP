---
title: 'Lync Server 2013: コマンドレットの使用によるドメインの準備の無効化'
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
ms.openlocfilehash: d72c135e7daccd677f8e42ea93a2aace8d7cafb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Lync Server 2013 のコマンドレットの使用によるドメインの準備の無効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

[無効にする] **-CsAdDomain**コマンドレットを使用して、ドメインの準備手順を逆にします。

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>コマンドレットを使用してドメインの準備を逆にするには

1.  Domain Admins グループのメンバーとして、ドメイン内の任意のサーバーにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    次に例を示します。
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Force パラメーターが存在する場合、ドメイン内の1つ以上のフロントエンドサーバーまたは A/V 会議サーバーがアクティブ化されている場合でも、ドメインの準備はロールバックされます。 Force パラメーターが存在しない場合、ドメイン内のフロントエンドサーバーまたは A/V 会議サーバーがアクティブ化されていると、ドメインの準備のロールバックが終了します。
    
    <div>
    

    > [!NOTE]  
    > Parameter GlobalSettingsDomainController を使うと、グローバル設定が保存されている場所を指定できます。 設定がシステムコンテナーに保存されている場合 (つまり、グローバル設定が構成コンテナーに移行されていないアップグレード展開で一般的)、Active Directory フォレストのルートでドメインコントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、設定は構成コンテナーに保存され、AD&nbsp;DS の任意のドメインコントローラーを参照することがコマンドレットによって想定されます。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のドメイン準備手続き](lync-server-2013-running-domain-preparation.md)  


[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

