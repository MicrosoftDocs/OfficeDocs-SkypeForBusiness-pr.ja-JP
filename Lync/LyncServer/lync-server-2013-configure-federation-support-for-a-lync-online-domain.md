---
title: 'Lync Server 2013: Lync Online ドメインのフェデレーションサポートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Lync Server 2013 での Lync Online ドメインのフェデレーションサポートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Microsoft Lync Online 2010 とのフェデレーションのお客様は、次の手順を完了する必要があります。

  - Lync Online 2010 顧客のドメイン (たとえば、contoso.onmicrosoft.com) のサポートを構成します。 このドキュメントの「lync [Server 2013 で Lync Online 顧客とのフェデレーションを行うための前提条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)」で説明されているように、組織のフェデレーションを既に有効にしている必要があります。 フェデレーションを有効にするには、フェデレーションドメインによるアクセスを制御するために使用するメソッドを指定する必要があります。 検出機能を使用するように組織を構成している場合、ドメインを組織の許可リストに追加するオプションは省略できます。 ドメインの検出を有効にしなかった場合は、Lync Online のユーザーのドメイン名を、許可ドメインの一覧に追加する必要があります。 ドメイン名を追加するには、Lync Server コントロールパネルを使用するか、または**新しい-CSAllowedDomain**コマンドレットを実行します。 Lync Server コントロールパネルの使用について詳しくは、「ドメインの検出を有効にする」をご覧ください。運用マニュアルの「 [Lync server 2013 で組織の SIP フェデレーションプロバイダーを管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)する」を参照してください。 **新しい-csalloweddomain**コマンドレットを使用してドメインを追加する方法について詳しくは、操作のドキュメントにある「[新しい-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 」をご覧ください。
    
    <div>
    

    > [!NOTE]  
    > Lync Online のユーザーは、複数のドメインを持つことができます。 複数のドメインとフェデレーションを行う場合は、フェデレーションをサポートする個々のドメインのサポートを構成する必要があります。また、Lync Online のユーザーの管理者がフェデレーションを有効にするには、それぞれのドメインに対してフェデレーションを有効にする必要があります。

    
    </div>

  - フェデレーションを行う Lync Online 2010 顧客ドメインのホスティングプロバイダーのサポートを構成します。 このセクションの手順を使用して、ホスティングプロバイダーのサポートを構成します。
    
    <div>
    

    > [!NOTE]  
    > この手順は、Lync Online の顧客のドメインとのフェデレーションの場合にのみ必要です。フェデレーションパートナーの場所にオンプレミスで展開されているドメインとのフェデレーションには使用できません。

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>ホスティングプロバイダーのサポートを構成するには

1.  フロントエンドサーバーから、Lync Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  **新しい-CsHostingProvider**コマンドレットを実行して、ホスティングプロバイダーを作成し、構成します。 たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述の例では、次のパラメーターが設定されます。
    
      - **Id**は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します。 既存のプロバイダーが既にその Id で構成されている場合、コマンドは失敗します。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 この値は変更できません。 ホスティングプロバイダーによってプロキシサーバーが変更された場合は、削除して、そのプロバイダーのエントリを再作成する必要があります。
    
      - **VerificationLevel**は、ホスティングプロバイダーから送信されたメッセージを、そのプロバイダーから送信されたものであるかどうかを確認するために、どのようにするかを指定します。
    
      - **Enabled ** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。この値を **True ** に設定しないと、2 つの組織間でメッセージを交換することはできません。
    
      - **EnabledSharedAddressSpace ** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
    
      - **Hostているユーザー**は、ホスティングプロバイダーが Lync Server アカウントをホストするために使用されているかどうかを示します。 **False ** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Lync server トポロジ内に含まれているかどうかを示します。
    
    このコマンドレットの使い方の詳細については、操作のドキュメントの「[新規-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

