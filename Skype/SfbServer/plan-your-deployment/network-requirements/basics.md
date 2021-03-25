---
title: DNS の基本
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 には、DNS サービスを提供できるソフトウェアが組み込まれています。そのため、DNS ポリシー シナリオ ガイドなどの使用可能なドキュメントを確認できます。 必要に応じて、サード パーティ製のソリューションを選択できます。
ms.openlocfilehash: 2e8655cb53228fbfe23bc62aaebbdfd5a02ce4f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116035"
---
# <a name="dns-basics"></a>DNS の基本
 
Windows Server 2016 には、DNS サービスを提供できるソフトウェアが組み込まれています。そのため、DNS ポリシー シナリオ ガイドなどの利用可能な [ドキュメントを確認することもできます](/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。 必要に応じて、サード パーティ製のソリューションを選択できます。
  
ベスト プラクティスとして、DNS を提供するために実装内の特定のサーバーを使用することをお勧めします。 Skype for Business サーバーの役割の 1 つ専用のサーバーの 1 つでセットアップできる可能性がありますが、そのサーバーもプールの一部であり、DNS サービスが再確立されるまで Skype for Business が誤動作して使用停止になっていた場合。
  
## <a name="dns-records"></a>DNS レコード

名前から IP アドレスへの各マッピング (IPv4 または IPv6 アドレスの場合があります) は、DNS サーバー上の DNS レコードに格納されます。 この名前は、DNS レポートで FQDN (完全修飾ドメイン名) として具体的に説明されています。 この *contoso.com* 有効なドメイン名ですが *\* 、.contoso.com* の短い名前なので、あいまいで、ドメイン内の任意のサーバーを参照する可能性があります。 ドメイン内の 1 つのサーバーを参照する FQDN の例は、次 **meeting01.contoso.com。**
  
> [!IMPORTANT]
> 既定では、ドメインに参加していないコンピューターのコンピューター名はホスト名であり、完全修飾ドメイン名 (FQDN) ではありません。 トポロジ ビルダーは、ホスト名ではなく FQDN を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。  Skype for Business Server を実行しているサーバーに FQDN を割り当てる場合は、標準文字 (A-Z、a-z、0-9、ハイフンを含む) のみを使用します。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。
  
IP アドレスに加えて、FQDN は VIP ( **仮想 IP** アドレス) にマップできます。 VIP は、実際の物理ネットワーク インターフェイスに対応しない IP アドレスです。 VIP は、多くの場合、サーバーの役割を実行するサーバーのプール、または冗長性とフォールト トレランス用に構成された一対のサーバーを示します。
  
DNS レコードにはいくつかの種類があります。この議論に最も関連する DNS レコードは次のとおりです。 
  
- **A** — アドレス レコードまたはホスト レコード、32 ビット IPv4 アドレスを返します。 ホスト名をホストの IP アドレスにマップするために最も一般的に使用されます。
    
- **AAAA** — IPv6 アドレス レコード。 128 ビットの IPv6 アドレスを返します。 ホスト名をホストの IP アドレスにマップするために最も一般的に使用されます。
    
- **CNAME** — 標準名レコード。 これにより、1 つの名前が別の名前に解決されます。DNS 参照は新しい名前で参照を再試行します。
    
- **SRV** — サービス レコード (SRV レコード) は、特定のポートと IP の組み合わせでアクセスされるサービス (サーバー上のプロセス) を指定します。 サービス レコードを必要とするサービスの名前は固定され、SIP ドメインの一部を超えてカスタマイズできません。 一部のユーザー サービスでは、単純な URL を使用します。 SRV レコードは同じ SIP ドメイン内の場所を指している必要があります。複数のドメインがある場合は、特定のサービスに対して複数の SRV レコードが必要になります。
    
## <a name="how-to-choose-a-sip-domain-name"></a>SIP ドメイン名を選択する方法
<a name="BK_NameSIP"> </a>

通常、組織の SIP ドメイン名は、ユーザーに与えられた電子メール アドレスと一致します。 組織内のユーザーが Brown@contoso.com のような電子メール アドレスを持つ場合は、contoso.com ドメイン名を持つ組織 \<sip-domain\> contoso.com。
  
### <a name="multiple-sip-domains"></a>複数の SIP ドメイン

 組織では、いくつかの SIP ドメインが必要な場合があります。 たとえば、Fabrikam.com が contoso.com によって取得された場合、Skype for Business Server が認識し、接続を受け入れる新しい SIP ドメインを作成する必要がある場合があります。 これを行う場合は、contoso.com を使用するすべての DNS レコードの追加セットを作成し、Fabrikam の要求を送信する場所を示す新しい FQDN を作成する必要があります。
  
## <a name="dns-load-balancing"></a>DNS 負荷分散
<a name="BK_NameSIP"> </a>

DNS を使用して、サーバー プールとして設定されている複数のサーバー間でトラフィック負荷を共有できます。 これを行うには、プールの FQDN に対して複数の A レコードを作成し、それぞれのレコードがプール内のノードの IP アドレスをポイントします。
  
負荷分散 [の詳細については、「DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 負荷分散」を参照してください。
