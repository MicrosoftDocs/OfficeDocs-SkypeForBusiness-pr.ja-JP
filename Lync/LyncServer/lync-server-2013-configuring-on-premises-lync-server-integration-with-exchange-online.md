---
title: オンプレミスの Lync Server と Exchange Online の統合の構成
description: オンプレミスの Lync Server と Exchange Online の統合を構成します。
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
ms.openlocfilehash: 59c612bcdcdf4803bd6f9f2b38f1f9bb7dbad016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553939"
---
# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>社内の Lync Server 2013 と Exchange Online との統合の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2018-03-30_

オンプレミスの Lync Server 2013 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Exchange Online の Microsoft Outlook Web App との相互運用性を構成できます。 相互運用性機能には、Outlook Web App インターフェイスとのシングルサインオン、インスタントメッセージング (IM)、プレゼンス統合が含まれます。 この統合を有効にするには、次のタスクを完了して、オンプレミスの Lync Server 展開でエッジサーバーを構成する必要があります。

  - 共有 SIP アドレススペースを構成する

  - エッジサーバーのホスティングプロバイダーを構成する

  - 更新された中央管理ストアのレプリケーションを確認する

Lync Server 2013 が Exchange Online と統合されている場合、OWA から IM にサインインしようとしているユーザーは、リモートユーザーまたは外部ユーザーと見なされます。 このシナリオでは、このユーザーに、次のオプションを選択した外部アクセスポリシーが割り当てられている必要があります。

**リモートユーザーとの通信を有効にする**

ユーザーがファイアウォールの外側にいて、在宅勤務中のユーザーなど、インターネット経由で Lync Server に接続できる組織内のユーザーがいる場合は、このオプションを有効にします。

詳細については、「 [Lync Server 2013 の外部アクセスポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)」を参照してください。

<div>

## <a name="configure-a-shared-sip-address-space"></a>共有 SIP アドレススペースを構成する

オンプレミスの Lync Server 2013 を Exchange Online と統合するには、共有 SIP アドレススペースを構成する必要があります。 Lync Server と Exchange Online サービスの両方で、同じ SIP ドメインアドレススペースがサポートされています。

Lync Server 管理シェルを使用して、次の例に示されているパラメーターを使用して、 **set-csaccessedgeconfiguration** コマンドレットを実行して、フェデレーション用にエッジサーバーを構成します。

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。 このプロパティは、内部ユーザーが Lync Server および Exchange Online を使用して、共有 SIP アドレススペースシナリオのユーザーと通信できるかどうかも決定します。

Lync Server 管理シェルの使用方法の詳細については、「 [Lync server 2013 Management shell](lync-server-2013-lync-server-management-shell.md)」を参照してください。

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>エッジサーバーのホスティングプロバイダーを構成する

Lync Server 管理シェルを使用して、エッジサーバーのホスティングプロバイダーを構成します。 これを行うには、次の例のパラメーターを使用して、 **新しい-CsHostingProvider** コマンドレットを実行します。

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> 中国で21Vianet が運用している Office 365 を使用している場合は、この例の <STRONG>Proxyfqdn</STRONG> パラメーター ("exap.um.outlook.com") の値を、21vianet が運用しているサービスの FQDN に置き換えます。 "exap.um.partner.outlook.cn"。



</div>

  - **Identity** は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します (例: "Exchange Online")。 スペースを含む値は、二重引用符で囲む必要があります。

  - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 **True**に設定する必要があります。

  - **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 **True**に設定する必要があります。

  - **Hostソケット Susers** は、ホスティングプロバイダーが Office Communications server または Lync Server をホストするために使用されているかどうかを示します。 この値は **False**に設定する必要があります。

  - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 Exchange Online の場合、FQDN は exap.um.outlook.com です。

  - **Islocal** は、ホスティングプロバイダーによって使用されるプロキシサーバーが Lync server トポロジ内に含まれているかどうかを示します。 この値は **False**に設定する必要があります。

  - **VerificationLevel** は、ホストされているプロバイダーとの間で送受信されるメッセージに対して許可される確認レベルを示します。 の **ように指定します**。 このオプションは、ホスティングプロバイダーから送信されるメッセージに含まれる検証レベルに依存します。 このレベルが指定されていない場合、メッセージは検証不能として拒否されます。

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>更新された中央管理ストアのレプリケーションを確認する

前のセクションのコマンドレットを使用して加えた変更は、エッジサーバーに自動的に適用され、通常はレプリケーションに1分未満かかります。 次のコマンドレットを使用して、レプリケーションの状態を確認し、変更がエッジサーバーに適用されたことを確認できます。

Lync Server 展開の内部サーバーでレプリケーションの更新を確認するには、次のコマンドレットを実行します。

    Get-CsManagementStoreReplicationStatus

変更が適用されたことを確認するには、エッジサーバーで次のコマンドレットを実行します。

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 ユーザーに hosted Exchange UM のボイスメールを提供する](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013 でのホスト型 Exchange ユニファイドメッセージングの統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
