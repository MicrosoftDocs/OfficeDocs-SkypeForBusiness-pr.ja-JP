---
title: Mac 版 Skype for Business クライアントの要件
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: このトピックでは、Mac で Skype for Business を実行する場合のハードウェア、ソフトウェア、およびインフラストラクチャの要件について説明します。
ms.openlocfilehash: 5f967bab3a5dcc41a3419324c9fe09b48a8fb674
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832167"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac 版 Skype for Business クライアントの要件
 
このトピックでは、Mac で Skype for Business を実行する場合のハードウェア、ソフトウェア、およびインフラストラクチャの要件について説明します。
  
[Skype for Business on Mac Client は](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac)ダウンロードできます。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac 上の Skype for Business のハードウェア要件およびソフトウェア要件

Mac 上の Skype for Business クライアントでは、Mac OS X El-1 以上が必要であり、100 MB 以上のディスク領域を使用します。 すべての組み込みのオーディオデバイスとビデオ デバイスの使用がサポートされています。 外部デバイスは [、Skype for Business ソリューション カタログに含む必要があります](https://partnersolutions.skypeforbusiness.com/solutionscatalog)。 
  
> [!NOTE]
> この一覧は暫定的であり、一部のデバイスは Lync の認定を受け取る場合がありますが、Mac の Skype for Business ではサポートされていません。 必要な最小 [ハードウェアについては、「](https://products.office.com/office-system-requirements) システム要件」を参照してください。
  
### <a name="legacy-mac-clients"></a>従来の Mac クライアント

Skype for Business Server 2015 は、Mac OS 10.5.8 または最新のサービス パックまたはリリース (Intel ベース) オペレーティング システムを実行しているコンピューターでも、次のレガシ クライアントをサポートしています (Mac OS 10.9 オペレーティング システムは現在サポートされていません)。 サポートされる機能の詳細については [、「Skype for Business のデスクトップ クライアント機能の比較」を参照してください](desktop-feature-comparison.md)。
  
- Microsoft Lync for Mac 2011 [(Lync for Mac 2011 展開ガイドを参照](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator for Mac 2011 (「Communicator for Mac 2011 [Deployment Guide」を参照)](https://go.microsoft.com/fwlink/p/?LinkId=268787)
 
これらのクライアントは、Skype for Business Server 2019 ではサポートされていません。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 上の Skype for Business のインフラストラクチャ要件
<a name="Infrastructure"> </a>

Skype for Business on Mac クライアントは、Unified Communications Management Platform (UCMP) と、モビリティ クライアントが使用する Unified Communications Web API (UCWA) の両方を利用します。
  
クライアントには、サポートされている構成でアクセス エッジ サーバーとリバース プロキシを展開する必要があるという点で、モビリティ クライアントと同じ要件があります。 
  
### <a name="authentication"></a>認証

Mac 上の Skype for Business クライアントは、展開および有効化時に証明書ベース認証、Microsoft モダン認証、および多要素認証をサポートします。
  
> [!NOTE]
> 現在の制限により、ユーザーの Exchange 資格情報は Skype for Business の資格情報と同じである必要があります。 
  
### <a name="certificates"></a>証明書

アクセス エッジ、リバース プロキシ、およびフロントエンド サーバーで使用されている証明書は、SHA-512 ハッシュ アルゴリズムを使用できません。
  
HTTP 証明書失効リストは、クライアントが定義してアクセスできる必要があります。 たとえば、証明書失効リストとして証明書内の LDAP エントリはサポートされていません。
  
### <a name="dns"></a>DNS

Mac クライアントで Skype for Business が正常に機能するには、モビリティを適切に展開する必要があります。 一般的な障害シナリオでは、内部ネットワークで次の両方の DNS エントリを解決できます。
  
- lyncdiscoverinternal。\<sipdomain\>
    
- lyncdiscover。\<sipdomain\>
    
詳細については [、「Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)でのモビリティの展開」および [「Microsoft Lync Server 2010 Mobility Guide」を参照してください](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>関連項目
<a name="Infrastructure"> </a>

[Skype for Business Server の DNS 要件](../../plan-your-deployment/network-requirements/dns.md)

[よく寄せられる質問](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[既知の問題](https://go.microsoft.com/fwlink/p/?LinkId=798228)
