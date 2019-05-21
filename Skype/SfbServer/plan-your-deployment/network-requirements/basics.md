---
title: DNS の基本
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 には、DNS サービスを提供できるソフトウェアが組み込まれているため、DNS ポリシーシナリオガイドなどの利用可能なドキュメントを確認することができます。 必要に応じて、サードパーティのソリューションを選ぶことができます。
ms.openlocfilehash: c1084a756a79ebcf15b8e99eef049690b5dcd9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297275"
---
# <a name="dns-basics"></a>DNS の基本
 
Windows Server 2016 には、DNS サービスを提供できるソフトウェアが組み込まれているため、 [Dns ポリシーシナリオガイド](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)などの利用可能なドキュメントを確認することができます。 必要に応じて、サードパーティのソリューションを選ぶことができます。
  
ベストプラクティスとして、実装の特定のサーバー専用の DNS を提供することをお勧めします。 Skype for Business server のいずれかの役割専用のサーバーの1つに設定することもできますが、そのサーバーがプールの一部であり、事故によって廃止された場合は、DNS サービスが再確立されるまで Skype for Business が誤動作する可能性があります。
  
## <a name="dns-records"></a>DNS レコード

IP アドレスへの名前の各マッピング (IPv4 アドレスまたは IPv6 アドレス) は、DNS サーバー上の DNS レコードに格納されます。 この名前は、特に FQDN (完全修飾ドメイン名) の DNS レポートで説明されています。 *Contoso.com*は有効なドメイン名ですが、 * \*contoso.com*の短縮形であるため、ドメイン内のサーバーを参照している可能性があります。 ドメイン内の1つのサーバーを参照する FQDN の例は、 **meeting01.contoso.com**である可能性があります。
  
> [!IMPORTANT]
> 既定では、ドメインに参加していないコンピューターのコンピューター名はホスト名であり、完全修飾ドメイン名 (FQDN) ではありません。 トポロジビルダーでは、ホスト名ではなく Fqdn を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で DNS サフィックスを構成する必要があります。 **標準文字のみを使用する**(A-z、a-z、0-9、ハイフンなど) を使用すると、Skype for Business Server を実行しているサーバーに Fqdn を割り当てることができます。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。
  
IP アドレスに加えて、FQDN は**VIP** (仮想 IP アドレス) に対応付けることができます。 VIP は、実際の物理ネットワークインターフェイスに対応しない IP アドレスです。 多くの場合、VIP は、サーバーの役割を実行しているサーバーのプール、または冗長性とフォールトトレランスを実現するように構成されたサーバーのペアを指します。
  
このディスカッションに最も関連性が高い DNS レコードには、次のようなものがあります。 
  
- **A** : アドレスレコードまたはホストレコードは、32ビット IPv4 アドレスを返します。 最も一般的には、ホストの IP アドレスへのホスト名のマッピングに使用されます。
    
- **AAAA** — IPv6 アドレスレコード。 128ビットの IPv6 アドレスを返します。 最も一般的には、ホストの IP アドレスへのホスト名のマッピングに使用されます。
    
- **CNAME** : 正式な名前レコード。 1つの名前が別の名前に解決されます。 DNS 参照は、新しい名前で参照をもう一度実行します。
    
- **Srv** -サービスレコード (SRV レコード) は、特定のポートと IP の組み合わせによってアクセスされるサービス (サーバー上のプロセス) を指定します。 サービスレコードを必要とするサービスの名前は修正され、SIP ドメインの一部を構成する以外にカスタマイズすることはできません。 一部のユーザーサービスでは、単純な Url を使用します。 SRV レコードは、同じ SIP ドメイン内の場所を指している必要があります。複数のドメインがある場合は、特定のサービスに対して複数の SRV レコードが必要になります。
    
## <a name="how-to-choose-a-sip-domain-name"></a>SIP ドメイン名の選択方法
<a name="BK_NameSIP"> </a>

通常、組織の SIP ドメイン名は、ユーザーに与えられたメールアドレスに合わせて配置されます。 組織内のユーザーが Brown@contoso.com のようなメールアドレスを持っている場合\<、contoso.com ドメイン\>名を持つ組織の優先 sip ドメインは単に contoso.com になります。
  
### <a name="multiple-sip-domains"></a>複数の SIP ドメイン

 組織によっては、複数の SIP ドメインが必要な場合があります。 たとえば、Fabrikam.com が contoso.com によって取得された場合は、Skype for Business Server で認識され、接続を受け入れる新しい SIP ドメインを作成することが必要な場合があります。 これを行うには、contoso.com を使用するすべての DNS レコードの追加のセットを作成する必要があります。これは、Fabrikam の要求を送信する場所を示す新しい Fqdn と共に指定する必要があります。
  
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BK_NameSIP"> </a>

DNS を使用して、サーバープールとして設定された複数のサーバー間でトラフィックの負荷を共有することができます。 これを行うには、プールの FQDN 用のレコードをいくつか作成します。各レコードは、プール内のノードの IP アドレスをポイントします。
  
ロードバランシングについて詳しくは、「 [DNS のロードバランシング](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)」をご覧ください。
  

