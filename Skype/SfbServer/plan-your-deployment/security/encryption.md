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
description: Skype for Business Server では、TLS と MTLS を使用してインスタント メッセージを暗号化します。 すべてのサーバー間トラフィックでは、トラフィックが内部ネットワークに限定されているのか、内部ネットワーク境界を越えた場合でも、MTLS が必要です。 Skype for Business Server をサードパーティの IPPBX システムまたは SIP トランク TLS に接続する場合は、オプションですが、仲介サーバーとメディア ゲートウェイの間で強く推奨されます。 このリンクで TLS が構成されている場合は、MTLS が必要です。 したがって、仲介サーバーによって信頼されている CA からの証明書を使用してゲートウェイを構成する必要があります。
ms.openlocfilehash: 269a5394f5438802c68dabed17081c71a353a2b5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104233"
---
# <a name="encryption-for-skype-for-business-server"></a>Skype for Business Server の暗号化
 
Skype for Business Server では、TLS と MTLS を使用してインスタント メッセージを暗号化します。 すべてのサーバー間トラフィックでは、トラフィックが内部ネットワークに限定されているのか、内部ネットワーク境界を越えた場合でも、MTLS が必要です。 Skype for Business Server をサードパーティの IPPBX システムまたは SIP トランク TLS に接続する場合は、オプションですが、仲介サーバーとメディア ゲートウェイの間で強く推奨されます。 このリンクで TLS が構成されている場合は、MTLS が必要です。 したがって、仲介サーバーによって信頼されている CA からの証明書を使用してゲートウェイを構成する必要があります。
  
> [!NOTE]
> SSL 3.0 に関するセキュリティ アドバイザリが 2014 年に公開されました。 Skype for Business Server 2015 での SSL 3.0 の無効化は、サポートされるオプションです。 セキュリティ アドバイザリの詳細については [、「Lync Server 2013 および Skype for Business Server 2015 での SSL 3.0](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013)の無効化」を参照してください。<br/>
**セキュリティに関する注意:** 最も強力な暗号化プロトコルを使用するために、Skype for Business Server 2015 は TLS 暗号化プロトコルをクライアントに提供します **。TLS 1.2 、TLS 1.1、TLS 1.0。** TLS は Skype for Business Server 2015 の重要な側面であり、サポートされている環境を維持するために必要です。<br/>
**セキュリティに関する注意:** 最も強力な暗号化プロトコルを使用するために、Skype for Business Server 2019 は、TLS 暗号化プロトコルをクライアントに次の順序で提供します **。TLS 1.3、TLS 1.2。** TLS は Skype for Business Server 2019 の重要な側面であり、サポートされている環境を維持するために必要です。 
  
次の表に、各種トラフィックのプロトコル要件をまとめます。 
  
**トラフィックの保護**

|**トラフィックの種類**|**保護用プロトコル**|
|:-----|:-----|
|サーバー間  <br/> |MTLS  <br/> |
|クライアントからサーバーへの接続  <br/> |TLS  <br/> |
|インスタント メッセージングおよびプレゼンス  <br/> |TLS  <br/> |
|オーディオとビデオ、およびメディアのデスクトップ共有  <br/> |SRTP  <br/> |
|デスクトップ共有 (シグナリング)  <br/> |TLS  <br/> |
|Web 会議  <br/> |TLS  <br/> |
|会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>メディアの暗号化

メディア トラフィックは、RTP トラフィックに機密性、認証、再生攻撃保護を提供する Real-Time トランスポート プロトコル (RTP) のプロファイルである Secure RTP (SRTP) を使用して暗号化されます。 さらに、仲介サーバーとその内部の次ホップの間で双方向に流れるメディアも、SRTP を使用して暗号化されます。 仲介サーバーとメディア ゲートウェイの間で両方向に流れるメディアは、必要に応じて暗号化され、推奨されます。 仲介サーバーはメディア ゲートウェイへの暗号化をサポートできますが、ゲートウェイは MTLS と証明書のストレージをサポートする必要があります。
  
> [!NOTE]
> ハイブリッドの設定の詳細については、「ハイブリッド接続の計画 [」を参照してください](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
  
## <a name="fips"></a>FIPS

Windows Server オペレーティング システムがシステム暗号化に FIPS 140-2 アルゴリズムを使用するように構成されている場合、Skype for Business Server および Microsoft Exchange Server 2016 は、連邦情報処理標準 (FIPS) 140-2 アルゴリズムをサポートします。 FIPS サポートを実装するには、Skype for Business Server を実行している各サーバーを構成してサポートする必要があります。
