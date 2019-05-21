---
title: Skype for Business Server の暗号化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server は、TLS と MTLS を使ってインスタントメッセージを暗号化します。 トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。 Skype for Business Server をサードパーティの IPPBX システムまたは SIP trunks TLS に接続する場合はオプションですが、仲介サーバーとメディアゲートウェイ間では強くお勧めします。 この接続に TLS を構成する場合は MTLS も必要です。 そのため、ゲートウェイは、仲介サーバーによって信頼されている CA からの証明書を使って構成する必要があります。
ms.openlocfilehash: 3aadc51dff7fafe32ea929cdec3d4f2f03ee92fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296918"
---
# <a name="encryption-for-skype-for-business-server"></a>Skype for Business Server の暗号化
 
Skype for Business Server は、TLS と MTLS を使ってインスタントメッセージを暗号化します。 トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。 Skype for Business Server をサードパーティの IPPBX システムまたは SIP trunks TLS に接続する場合はオプションですが、仲介サーバーとメディアゲートウェイ間では強くお勧めします。 この接続に TLS を構成する場合は MTLS も必要です。 そのため、ゲートウェイは、仲介サーバーによって信頼されている CA からの証明書を使って構成する必要があります。
  
> [!NOTE]
> SSL 3.0 に関するセキュリティ アドバイザリが 2014 年に公開されました。 Skype for Business Server 2015 での SSL 3.0 の無効化は、サポートされています。 セキュリティアドバイザリの詳細については、「 [Lync server 2013 および Skype For Business server 2015 での SSL 3.0 の無効化](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)」を参照してください。<br/>
**セキュリティメモ:** 最強の暗号化プロトコルを使用するために、Skype for Business Server 2015 は次の順序で TLS 暗号化プロトコルをクライアントに提供します。 **tls 1.2、tls 1.1、tls 1.0**。 TLS は Skype for Business Server 2015 の重要な側面であり、サポートされている環境を維持するために必要です。<br/>
**セキュリティメモ:** 最強の暗号化プロトコルを使用するために、Skype for Business Server 2019 は次の順序で TLS 暗号化プロトコルをクライアントに提供します。 tls **1.3、tls 1.2**。 TLS は Skype for Business Server 2019 の重要な側面であり、サポートされている環境を維持するために必要です。 
  
次の表に、各種トラフィックのプロトコル要件をまとめます。 
  
**トラフィックの保護**

|**トラフィックの種類**|**保護用プロトコル**|
|:-----|:-----|
|サーバー間  <br/> |MTLS  <br/> |
|クライアントからサーバー  <br/> |TLS  <br/> |
|インスタント メッセージングとプレゼンス  <br/> |TLS   <br/> |
|オーディオとビデオ、メディアのデスクトップ共有  <br/> |SRTP  <br/> |
|デスクトップ共有 (シグナリング)  <br/> |TLS  <br/> |
|Web 会議  <br/> |TLS  <br/> |
|会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>メディアの暗号化

メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。これは、秘密保持機能、認証、RTP トラフィックなどに対する再生攻撃からの保護機能を提供するリアルタイム転送プロトコル (RTP) のプロファイルです。さらに、仲介サーバーとその次のホップ間で双方向にやりとりされるメディアも SRTP を使用して暗号化されます。仲介サーバーとメディア ゲートウェイ間で双方向にやりとりされるメディアはオプションで暗号化され、暗号化することが推奨されます。仲介サーバーはメディア ゲートウェイに対する暗号化をサポートできますが、ゲートウェイは MTLS および証明書のストレージをサポートする必要があります。
  
> [!NOTE]
> ハイブリッドの設定の詳細については、「[ハイブリッド接続の計画](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」を参照してください。
  
## <a name="fips"></a>FIPS

Skype for Business Server および Microsoft Exchange Server 2016 は、Windows Server オペレーティングシステムがシステム暗号化用の FIPS 140-2 アルゴリズムを使用するように構成されている場合に、米国連邦情報処理標準 (FIPS) 140-2 アルゴリズムのサポートで動作します。. FIPS サポートを実装するには、Skype for Business Server を実行している各サーバーでサポートされるように構成する必要があります。
  

