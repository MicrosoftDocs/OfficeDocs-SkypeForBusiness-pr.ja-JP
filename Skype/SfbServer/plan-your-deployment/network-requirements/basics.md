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
description: Windows Server 2016 には DNS サービスを提供できるソフトウェアが組み込まれています。そのため、DNS ポリシー シナリオ ガイドなどの利用可能なドキュメントを確認できます。 必要に応じて、サード パーティ製のソリューションを選択できます。
ms.openlocfilehash: dc60bab84220cad306deee408a6a09fc16df5a10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825587"
---
# <a name="dns-basics"></a>DNS の基本
 
Windows Server 2016 には DNS サービスを提供できるソフトウェアが組み込まれています。そのため [、DNS](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)ポリシー シナリオ ガイドなどの利用可能なドキュメントを確認できます。 必要に応じて、サード パーティ製のソリューションを選択できます。
  
ベスト プラクティスとして、DNS を提供するために実装内の特定のサーバーを使用することをお勧めします。 Skype for Business サーバーの役割の 1 つ専用のサーバーの 1 つでセットアップできる可能性がありますが、そのサーバーもプールの一部であり、誤って Skype for Business が使用停止になっていた場合は、DNS サービスが再確立されるまで正常に機能しなけれなっていた可能性があります。
  
## <a name="dns-records"></a>DNS レコード

IP アドレスへの名前のマッピング (および IPv4 または IPv6 アドレスの可能性がある) は、DNS サーバー上の DNS レコードに格納されます。 この名前は、DNS レポートで、具体的には FQDN (完全修飾ドメイン名) として記述されます。 この *contoso.com* 有効なドメイン名ですが *\* 、.contoso.com* の短い形式なので、あいまいで、ドメイン内の任意のサーバーを参照する可能性があります。 ドメイン内の 1 つのサーバーを参照する FQDN の例は、次 **meeting01.contoso.com。**
  
> [!IMPORTANT]
> 既定では、ドメインに参加していないコンピューターのコンピューター名はホスト名であり、完全修飾ドメイン名 (FQDN) ではありません。 トポロジ ビルダーでは、ホスト名ではなく FQDN を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。 Skype for Business Server を実行しているサーバーに FQDN を割り当てる場合は、標準文字 **(A** ~ Z、a ~ z、0 ~ 9、およびハイフンを含む) のみを使用します。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。
  
IP アドレスに加えて、FQDN は **VIP** (仮想 IP アドレス) にマップできます。 VIP は、実際の物理ネットワーク インターフェイスに対応しない IP アドレスです。 VIP は、多くの場合、サーバーの役割を実行するサーバーのプール、または冗長性とフォールト トレランス用に構成されたサーバーのペアをポイントします。
  
DNS レコードにはいくつかの種類があります。この説明に最も関連する DNS レコードは次のとおりです。 
  
- **A** — Address レコードまたは Host レコード。32 ビット IPv4 アドレスを返します。 ホスト名をホストの IP アドレスにマップするために最も一般的に使用されます。
    
- **AAAA** — IPv6 アドレス レコード。 128 ビット IPv6 アドレスを返します。 ホスト名をホストの IP アドレスにマップするために最も一般的に使用されます。
    
- **CNAME** — 正規名レコード。 これにより、1 つの名前が別の名前に解決されます。DNS 参照は新しい名前で検索を再試行します。
    
- **SRV** — サービス レコード (SRV レコード) は、特定のポートと IP の組み合わせでアクセスされるサービス (サーバー上のプロセス) を指定します。 サービス レコードを必要とするサービスの名前は固定され、SIP ドメインの一部以外にカスタマイズできません。 一部のユーザー サービスでは簡易 URL を使用します。 SRV レコードは同じ SIP ドメイン内の場所を指している必要があります。したがって、複数のドメインがある場合は、特定のサービスに複数の SRV レコードが必要になります。
    
## <a name="how-to-choose-a-sip-domain-name"></a>SIP ドメイン名を選択する方法
<a name="BK_NameSIP"> </a>

組織の SIP ドメイン名は、通常、ユーザーに与えられた電子メール アドレスと一致します。 組織内のユーザーが Brown@contoso.com のような電子メール アドレスを持つ場合、contoso.com ドメイン名を持つ組織の優先は単に \<sip-domain\> contoso.com。
  
### <a name="multiple-sip-domains"></a>複数の SIP ドメイン

 組織によっては、複数の SIP ドメインが必要になる場合があります。 たとえば、Fabrikam.com が contoso.com によって取得された場合、Skype for Business Server が認識し、接続を受け入れる新しい SIP ドメインを作成する必要がある場合があります。 これを行う場合は、fabrikam の要求を送信する場所を示す新しい FQDN を使用して、contoso.com を使用する DNS レコードの追加セットを作成する必要があります。
  
## <a name="dns-load-balancing"></a>DNS 負荷分散
<a name="BK_NameSIP"> </a>

DNS を使用して、サーバー プールとして設定されている複数のサーバー間でトラフィック負荷を共有できます。 これを行うには、プールの FQDN に対して複数の A レコードを作成し、各レコードがプール内のノードの IP アドレスをポイントします。
  
負荷分散 [の詳細については、「DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 負荷分散」を参照してください。
  

