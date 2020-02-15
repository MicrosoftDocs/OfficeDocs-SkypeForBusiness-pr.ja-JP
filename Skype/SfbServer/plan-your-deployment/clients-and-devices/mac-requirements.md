---
title: Mac クライアント上の Skype for Business の要件
ms.author: v-lanac
author: lanachin
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
description: このトピックでは、Mac で Skype for Business を実行するためのハードウェア、ソフトウェア、およびインフラストラクチャの要件について説明します。
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013460"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac クライアント上の Skype for Business の要件
 
このトピックでは、Mac で Skype for Business を実行するためのハードウェア、ソフトウェア、およびインフラストラクチャの要件について説明します。
  
[Mac 版 Skype For Business クライアント](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac)はダウンロードできます。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac 版 Skype for business のハードウェアおよびソフトウェア要件

Mac 版 Skype for Business クライアントでは、Mac OS X El Capitan 以上が必要です。また、少なくとも100MB のディスク領域が使用されます。 すべての組み込みのオーディオおよびビデオデバイスの使用をサポートしています。 外部デバイスは、 [Skype For Business ソリューションカタログ](https://partnersolutions.skypeforbusiness.com/solutionscatalog)に含まれている必要があります。 
  
> [!NOTE]
> このリストは暫定版であり、一部のデバイスは Lync 用に認定されていますが、Mac では Skype for Business ではサポートされていません。 必要な最小限のハードウェアの[システム要件](https://products.office.com/office-system-requirements)を参照してください。
  
### <a name="legacy-mac-clients"></a>従来の Mac クライアント

また、Skype for Business Server 2015 は、Mac OS 10.5.8 以降または最新のサービスパックやリリース (Intel ベース) オペレーティングシステムを実行しているコンピューターで、次のレガシクライアントもサポートしています (Mac OS 10.9 オペレーティングシステムは現在サポートされていません)。 サポートされる機能の詳細については、「Skype for business[のデスクトップクライアント機能の比較](desktop-feature-comparison.md)」を参照してください。
  
- Microsoft Lync for Mac 2011 (「 [Lync For mac 2011 展開ガイド」を](https://go.microsoft.com/fwlink/p/?LinkId=268786)参照してください)
    
- Microsoft Communicator for Mac 2011 (「 [Communicator For mac 2011 展開ガイド」を](https://go.microsoft.com/fwlink/p/?LinkId=268787)参照してください)
 
これらのクライアントは、Skype for Business Server 2019 ではサポートされていません。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 版 Skype for Business のインフラストラクチャ要件
<a name="Infrastructure"> </a>

Mac 版 Skype for Business クライアントは、統合コミュニケーション管理プラットフォーム (UCMP) と、モビリティクライアントが使用する統合コミュニケーション Web API (UCMP) の両方を活用しています。
  
クライアントには、サポートされている構成でアクセスエッジサーバーとリバースプロキシが展開されている必要があるという、のモビリティクライアントと同じ要件があります。 
  
### <a name="authentication"></a>認証

Mac 版 Skype for Business クライアントは、証明書ベースの認証、Microsoft モダン認証、および多要素認証が展開されて有効になっているときにサポートされます。
  
> [!NOTE]
> 現在の制限により、ユーザーの Exchange 資格情報は、Skype for Business の資格情報と同じである必要があります。 
  
### <a name="certificates"></a>証明書

アクセスエッジサーバー、リバースプロキシサーバー、フロントエンドサーバーで使用されている証明書は、512ハッシュアルゴリズムを使用してはなりません。
  
HTTP 証明書失効リストは、クライアントによって定義され、アクセス可能である必要があります。 たとえば、証明書の LDAP エントリを証明書失効リストとしてサポートしていません。
  
### <a name="dns"></a>DNS

モビリティは、適切に機能するように、Mac クライアント上の Skype for Business に適切に展開されている必要があります。 一般的なエラーシナリオは、次の両方の DNS エントリを内部ネットワークで解決可能にすることです。
  
- lyncdiscoverinternal.\<microsoft.rtc.management.xds.sipdomain\>
    
- lyncdiscover.\<microsoft.rtc.management.xds.sipdomain\>
    
詳細については、「 [Lync server 2013 でのモビリティの展開](https://go.microsoft.com/fwlink/p/?LinkId=798224)」および「 [Microsoft Lync Server 2010 mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226)」を参照してください。
  
## <a name="see-also"></a>関連項目
<a name="Infrastructure"> </a>

[Skype for Business Server の DNS 要件](../../plan-your-deployment/network-requirements/dns.md)

[よく寄せられる質問](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[既知の問題](https://go.microsoft.com/fwlink/p/?LinkId=798228)
