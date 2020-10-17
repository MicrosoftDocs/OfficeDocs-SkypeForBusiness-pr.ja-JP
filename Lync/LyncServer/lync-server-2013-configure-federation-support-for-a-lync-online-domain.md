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
ms.openlocfilehash: 27780806e064aae82aa36cee96d9fafcdba2eddb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525974"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Lync Server 2013 で Lync Online ドメインのフェデレーションサポートを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Microsoft Lync Online 2010 を使用してフェデレーションを行うには、次の手順を完了する必要があります。

  - Lync Online 2010 お客様のドメインのサポートを構成します (たとえば、contoso.onmicrosoft.com)。 このドキュメントの「lync [Online の2013顧客とのフェデレーションの前提条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) 」に記載されているように、組織のフェデレーションが既に有効になっている必要があります。 フェデレーションを有効にするには、フェデレーション ドメインによってアクセス制御に使用されるメソッドを指定する必要があります。 検出を使用するように組織を構成した場合は、組織の許可リストへのドメインの追加は省略できます。 ドメインの検出を有効にしなかった場合は、Lync Online のユーザーのドメイン名を許可されたドメインの一覧に追加する必要があります。 ドメイン名を追加するには、Lync Server コントロールパネルを使用するか、または **新しい-CSAllowedDomain** コマンドレットを実行します。 ドメインの検出を有効にするなど、Lync Server コントロールパネルの使用の詳細については、「操作」のドキュメントの「 [MANAGE SIP フェデレーションプロバイダー for Your Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) 」を参照してください。 **新しい-csalloweddomain**コマンドレットを使用してドメインを追加する方法の詳細については、「操作」のドキュメントの「 [New-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > Lync Online のお客様は複数のドメインを持つことができます。 複数のドメインとフェデレーションを行う場合は、フェデレーションをサポートする個々のドメインのサポートを構成する必要があり、Lync Online のお客様の管理者は各ドメインのフェデレーションを有効にする必要があります。

    
    </div>

  - フェデレーションを行う Lync Online 2010 お客様のドメインのホスティングプロバイダーのサポートを構成します。 ホスティング プロバイダーのサポートを構成するには、このセクションの手順に従います。
    
    <div>
    

    > [!NOTE]  
    > この手順は、Lync Online のドメインとのフェデレーションにのみ必要であり、フェデレーションパートナーの場所に社内に展開されたドメインとのフェデレーションには必要ありません。

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>ホスティング プロバイダーのサポートを構成するには

1.  フロントエンドサーバーから、Lync Server 管理シェルを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを作成および構成します。 たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上記の例では、次のパラメーターを設定しています。
    
      - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値 からなる識別子を指定します。既存のプロバイダーがその ID で既に構成されている場合、このコマンドの実行は失敗します。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **VerificationLevel** は、メッセージがホスティング プロバイダーから送信されたことを確認するために、そのプロバイダーから送信されたメッセージの検証方法 (または検証の有無) を指定します。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効かどうかを示します。この値を **True** に設定しないと、2 つの組織間でメッセージを交換できません。
    
      - **EnabledSharedAddressSpace** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
    
      - **Hostソケットのユーザー** は、ホスティングプロバイダーが Lync Server アカウントをホストするために使用されるかどうかを示します。 **False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **Islocal** は、ホスティングプロバイダーによって使用されるプロキシサーバーが Lync server トポロジ内に含まれているかどうかを示します。
    
    このコマンドレットの使用の詳細については、「操作」のドキュメントの「 [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

