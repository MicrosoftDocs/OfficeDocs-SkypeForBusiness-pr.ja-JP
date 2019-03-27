---
title: DNS の基礎
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 には、DNS ポリシーのシナリオ ガイドなどの使用可能なドキュメントを確認することがありますので、DNS サービスを提供する組み込みのソフトウェアがあります。 使用する場合は、サードパーティ製のソリューションが存在することができます。
ms.openlocfilehash: 2ba20c6aabd296f13ea5e84053d140123097f114
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886614"
---
# <a name="dns-basics"></a>DNS の基礎
 
Windows Server 2016 には、 [DNS ポリシー シナリオ ガイド](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)などの使用可能なドキュメントを確認することがありますので、DNS サービスを提供する組み込みのソフトウェアがあります。 使用する場合は、サードパーティ製のソリューションが存在することができます。
  
ベスト プラクティスとして専用にすること、特定のサーバーの実装では DNS を提供することをお勧めします。 でした可能性のある設定するビジネス サーバーの役割、そのサーバーがプールの一部であったもしが使用停止の状態、偶然 Skype ビジネスは、DNS サービスが再確立されるまで動作不良の場合ですが、Skype のいずれかの専用サーバーの 1 つにします。
  
## <a name="dns-records"></a>DNS レコード

IP アドレスの名前の各マッピング (およびある IPv4 または IPv6 アドレス) DNS サーバーの DNS レコードに格納されます。 名前が FQDN として具体的には、DNS レポートに記載されている、完全修飾ドメイン名です。 省略形が*contoso.com*では、有効なドメイン名ですが、 * \*. contoso.com* 、あいまいであり、ドメイン内のサーバーを参照可能性がありますので。 ドメイン内の 1 台のサーバーを参照して、FQDN の例には、 **meeting01.contoso.com**可能性があります。
  
> [!IMPORTANT]
> 既定ドメインに参加していないコンピューターのコンピューター名は、ホスト名としない、完全修飾ドメイン名 (FQDN) です。 トポロジ ビルダーでは、ホスト名ではなく、Fqdn を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で DNS サフィックスを構成する必要があります。 **唯一の標準文字を使用**(A-Z、a-z、0-9、およびハイフンを含む) Skype をビジネスのサーバーを実行しているサーバーに Fqdn を割り当てるとします。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。
  
IP アドレスだけでなく、FQDN にマップでした**VIP** -仮想 IP アドレスです。 VIP は、実際の物理ネットワーク インターフェイスに対応していない IP アドレスです。 または 2 つの冗長性とフォールト トレランス用に構成されたサーバーのサーバーの役割を実行しているサーバーのプールに多くの場合、VIP がポイントします。
  
DNS レコードのいくつかの種類があります、ここに最も関連するもの。 
  
- **A** :、レコードのアドレスまたはホストのレコードは、32 ビットの IPv4 アドレスを返します。 ホストの IP アドレスにホスト名をマップするのには最もよく使用されます。
    
- **AAAA** -IPv6 アドレス レコードです。 128 ビットの IPv6 アドレスを返します。 ホストの IP アドレスにホスト名をマップするのには最もよく使用されます。
    
- **CNAME** -標準的な名前のレコードです。 これ 1 つの名前別: DNS 参照は、新しい名前で検索を再試行します。
    
- **SRV** -サービス レコード (SRV レコード) は、特定のポートと IP の組み合わせにアクセスされているサービス (サーバー上のプロセス) を指定します。 サービス レコードを必要とするサービスの名前が固定で、それをする以外はカスタマイズできません、SIP ドメインの一部です。 ユーザーの一部のサービスでは、単純な Url を使用します。 SRV レコードは、特定のサービスに対して複数の SRV レコードを必要がありますドメインが複数ある場合、同じ SIP ドメイン内の場所にポイントする必要があります。
    
## <a name="how-to-choose-a-sip-domain-name"></a>SIP ドメイン名を選択する方法
<a name="BK_NameSIP"> </a>

組織の SIP ドメイン名は、通常そのユーザーに電子メール アドレスを配置します。 Brown@contoso.com、優先のような電子メール アドレスがある組織内のユーザーの場合\<sip ドメイン\>contoso.com ドメインと組織の名前は単に contoso.com です。
  
### <a name="multiple-sip-domains"></a>複数の SIP ドメイン

 組織必要がある場合によっては複数の SIP ドメイン。 たとえば、contoso.com、Fabrikam.com が買収した場合する必要があります Skype ビジネス サーバーを認識してからの接続はそのまま使用する新しい SIP ドメインを作成します。 これを行うときは、contoso.com を使用して、fabrikam 社の要求を送信する場所を表示する新しい Fqdn を持つすべての DNS レコードのセットを作成する必要があります。
  
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BK_NameSIP"> </a>

サーバー プールとして設定されているいくつかのサーバー間でトラフィックの負荷を共有するのには DNS を使用することができます。 これを行うで作成するいくつかの A レコード プールの FQDN をプール内のノードの IP アドレスを指すのです。
  
負荷分散の追加の説明については、 [DNS の負荷分散](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)を参照してください。
  

