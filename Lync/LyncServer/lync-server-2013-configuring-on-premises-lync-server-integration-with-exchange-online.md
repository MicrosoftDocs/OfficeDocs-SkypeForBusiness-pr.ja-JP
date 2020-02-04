---
title: Exchange Online とのオンプレミス Lync Server との統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a652fea6c54592526047e8d8b35a0bddd0ef1995
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>オンプレミスの Lync Server 2013 と Exchange Online の統合を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2018-03-30_

オンプレミスの Lync Server 2013 の展開を使用しているユーザーは、ハイブリッド展開モードで Microsoft Exchange Online の Microsoft Outlook Web App との相互運用性を構成できます。 相互運用性機能には、シングル サインオンが含まれるほか、Outlook Web App インターフェイスとのインスタント メッセージングおよびプレゼンスの統合が含まれます。 この統合を有効にするには、次のタスクを実行して、オンプレミスの Lync Server 展開でエッジサーバーを構成する必要があります。

  - 共有 SIP アドレス スペースを構成する

  - エッジサーバーでホスティングプロバイダーを構成する

  - 更新された中央管理ストアのレプリケーションを確認する

Lync Server 2013 が Exchange Online と統合されている場合、OWA から IM にサインインしようとしているユーザーは、リモートユーザーまたは外部ユーザーと見なされます。 このシナリオでは、このユーザーは、次のオプションが選択されている外部アクセスポリシーが割り当てられている必要があります。

**リモートユーザーとの通信を有効にする**

出張中の在宅勤務者やユーザーなど、組織内のユーザーがインターネット経由で Lync Server に接続できるようにする場合は、このオプションを有効にします。

詳細については、「 [Lync Server 2013 で外部アクセスポリシーを管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)する」を参照してください。

<div>

## <a name="configure-a-shared-sip-address-space"></a>共有 SIP アドレス スペースを構成する

オンプレミスの Lync Server 2013 を Exchange Online と統合するには、共有 SIP アドレス空間を構成する必要があります。 同じ SIP ドメインアドレス空間は、Lync Server と Exchange Online サービスの両方でサポートされています。

Lync Server 管理シェルを使用して、次の例に示すパラメーターを使用して、 **CSAccessEdgeConfiguration**コマンドレットを実行して、フェデレーション用にエッジサーバーを構成します。

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers ** は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。 このプロパティは、内部ユーザーが Lync Server および Exchange Online を使用して、共有 SIP アドレス空間のシナリオでユーザーと通信できるかどうかも決定します。

Lync Server 管理シェルの使い方の詳細については、「 [Lync server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」を参照してください。

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>エッジ サーバーにホスティング プロバイダーを構成する

Lync Server 管理シェルを使用して、エッジサーバーでホスティングプロバイダーを構成します。 これを行うには、次の例のパラメーターを使用して、**新しい-CsHostingProvider**コマンドレットを実行します。

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> 中国の 21Vianet により運営されている Office 365 を使用している場合は、この例の <STRONG>ProxyFqdn</STRONG> パラメーターの値 ("exap.um.outlook.com") を、21Vianet により運営されているサービスの FQDN である "exap.um.partner.outlook.cn" に置き換えます。



</div>

  - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値から成る識別子を指定します (例: "Exchange Online")。 スペースを含む値は二重引用符で囲む必要があります。

  - **Enabled ** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 これは**True**に設定する必要があります。

  - **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 これは**True**に設定する必要があります。

  - **Hostているユーザー**は、ホスティングプロバイダーが Office Communications server または Lync Server をホストするために使用されているかどうかを示します。 この値は**False**に設定する必要があります。

  - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 Exchange Online の FQDN は exap.um.outlook.com です。

  - **Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Lync server トポロジ内に含まれているかどうかを示します。 この値は**False**に設定する必要があります。

  - **VerificationLevel**は、ホストされているプロバイダーとの間で送受信されるメッセージに対して許可される確認レベルを示します。 Sns の**確認**を指定します。 このオプションは、ホスティングプロバイダーから送信されるメッセージに含まれている確認レベルに依存します。 このレベルが指定されていない場合、メッセージは、確認不能として拒否されます。

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>更新された中央管理ストアのレプリケーションを確認する

前のセクションのコマンドレットを使用して行った変更は、自動的にエッジサーバーに適用され、複製には1分未満かかります。 次のコマンドレットを使用して、レプリケーションの状態を確認し、変更がエッジサーバーに適用されたことを確認できます。

Lync Server の展開でサーバー上のレプリケーションの更新を確認するには、次のコマンドレットを実行します。

    Get-CsManagementStoreReplicationStatus

変更が適用されたことを確認するには、エッジサーバーで次のコマンドレットを実行します。

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 ユーザーに Hosted Exchange UM のボイス メールを提供する](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013 の Hosted Exchange ユニファイド メッセージング統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

