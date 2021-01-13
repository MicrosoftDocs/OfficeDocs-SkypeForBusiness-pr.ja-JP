---
title: Skype for Business Server の暗号化
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server は、TLS と MTLS を使用してインスタント メッセージを暗号化します。 すべてのサーバー間トラフィックでは、トラフィックが内部ネットワークに限定されているのか、内部ネットワーク境界を越えるのかにかかわらず、MTLS が必要です。 Skype for Business Server をサードパーティの IPPBX システムまたは SIP トランク TLS に接続する場合はオプションですが、仲介サーバーとメディア ゲートウェイの間での接続を強く推奨します。 このリンクで TLS が構成されている場合は、MTLS が必要です。 したがって、仲介サーバーによって信頼されている CA からの証明書を使用してゲートウェイを構成する必要があります。
ms.openlocfilehash: 48af03d7f6aed5b744ad4e0c460622194a87d96e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832207"
---
# <a name="encryption-for-skype-for-business-server"></a>Skype for Business Server の暗号化
 
Skype for Business Server は、TLS と MTLS を使用してインスタント メッセージを暗号化します。 すべてのサーバー間トラフィックでは、トラフィックが内部ネットワークに限定されているのか、内部ネットワーク境界を越えるのかにかかわらず、MTLS が必要です。 Skype for Business Server をサード パーティ製 IPPBX システムまたは SIP トランク TLS に接続する場合はオプションですが、仲介サーバーとメディア ゲートウェイの間の接続を強く推奨します。 このリンクで TLS が構成されている場合は、MTLS が必要です。 したがって、仲介サーバーによって信頼されている CA からの証明書を使用してゲートウェイを構成する必要があります。
  
> [!NOTE]
> SSL 3.0 に関するセキュリティ アドバイザリは、2014 年に公開されました。 Skype for Business Server 2015 で SSL 3.0 を無効にすることもできます。 セキュリティ アドバイザリの詳細については [、「Lync Server 2013 および Skype for Business Server 2015 での SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)の無効化」を参照してください。<br/>
**セキュリティに関するメモ:** 最も強力な暗号化プロトコルを使用するために、Skype for Business Server 2015 は TLS 暗号化プロトコルをクライアントに提供します **。TLS 1.2、TLS 1.1、TLS 1.0。** TLS は Skype for Business Server 2015 の重要な側面であり、サポートされている環境を維持するために必要です。<br/>
**セキュリティに関するメモ:** 最も強力な暗号化プロトコルを使用するために、Skype for Business Server 2019 は TLS 暗号化プロトコルをクライアントに提供します **。TLS 1.3、TLS 1.2。** TLS は Skype for Business Server 2019 の重要な側面であり、サポートされている環境を維持するために必要です。 
  
次の表に、各種トラフィックのプロトコル要件をまとめます。 
  
**トラフィックの保護**

|**トラフィックの種類**|**保護用プロトコル**|
|:-----|:-----|
|サーバー間  <br/> |MTLS  <br/> |
|クライアントからサーバー  <br/> |TLS  <br/> |
|インスタント メッセージングおよびプレゼンス  <br/> |TLS  <br/> |
|オーディオとビデオ、およびメディアのデスクトップ共有  <br/> |SRTP  <br/> |
|デスクトップ共有 (シグナリング)  <br/> |TLS  <br/> |
|Web 会議  <br/> |TLS  <br/> |
|会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>メディアの暗号化

メディア トラフィックは、RTP トラフィックに機密性、認証、リプレイ攻撃保護を提供する Real-Time トランスポート プロトコル (RTP) のプロファイルである Secure RTP (SRTP) を使用して暗号化されます。 さらに、仲介サーバーとその内部の次ホップの間で双方向に流れるメディアも、SRTP を使用して暗号化されます。 仲介サーバーとメディア ゲートウェイの間で両方向に流れるメディアは、必要に応じて暗号化され、推奨されます。 仲介サーバーはメディア ゲートウェイへの暗号化をサポートできますが、ゲートウェイは MTLS と証明書の保存をサポートする必要があります。
  
> [!NOTE]
> ハイブリッドの設定の詳細については、「ハイブリッド接続を計画 [する」を参照してください](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
  
## <a name="fips"></a>FIPS

Windows Server オペレーティング システムがシステム暗号化に FIPS 140-2 アルゴリズムを使用するように構成されている場合、Skype for Business Server および Microsoft Exchange Server 2016 は Federal Information Processing Standard (FIPS) 140-2 アルゴリズムのサポートと一緒に動作します。 FIPS サポートを実装するには、Skype for Business Server を実行している各サーバーを構成してサポートする必要があります。
  

