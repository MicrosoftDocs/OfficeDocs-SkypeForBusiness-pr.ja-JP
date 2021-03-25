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
description: このトピックでは、Mac で Skype for Business を実行するハードウェア、ソフトウェア、インフラストラクチャの要件について説明します。
ms.openlocfilehash: 866eda0cc5e82db1da1b69bee3eb4bf26df6d7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109283"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac 版 Skype for Business クライアントの要件
 
このトピックでは、Mac で Skype for Business を実行するハードウェア、ソフトウェア、インフラストラクチャの要件について説明します。
  
[Skype for Business on Mac Client を](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac)ダウンロードできます。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Skype for Business on Mac のハードウェア要件とソフトウェア要件

Skype for Business on Mac クライアントでは、Mac OS X El Capitan 以上が必要で、少なくとも 100 MB 以上のディスク領域を使用します。 すべての組み込みのオーディオデバイスとビデオ デバイスの使用をサポートしています。 外部デバイスは [、Skype for Business ソリューション カタログにある必要があります](https://partnersolutions.skypeforbusiness.com/solutionscatalog)。 
  
> [!NOTE]
> このリストは予備的なリストであり、一部のデバイスは Lync の資格を持つ可能性がありますが、Mac の Skype for Business ではサポートされていません。 必要な最小ハードウェア [については、「System requirements」](https://products.office.com/office-system-requirements) を参照してください。
  
### <a name="legacy-mac-clients"></a>従来の Mac クライアント

Skype for Business Server 2015 では、Mac OS 10.5.8 または最新のサービス パックまたはリリース (Intel ベース) オペレーティング システム (Mac OS 10.9 オペレーティング システムは現在サポートされていません) を実行しているコンピューターで、次の従来のクライアントもサポートしています。 サポートされる機能の詳細については [、「Skype for Business のデスクトップ クライアント機能の比較」を参照してください](desktop-feature-comparison.md)。
  
- Microsoft Lync for Mac 2011 [(「Lync for Mac 2011 Deployment Guide」を参照)](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14))
    
- Microsoft Communicator for Mac 2011 (「Communicator for Mac 2011 [展開ガイド」を参照してください](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14)))
 
これらのクライアントは、Skype for Business Server 2019 ではサポートされていません。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 上の Skype for Business のインフラストラクチャ要件
<a name="Infrastructure"> </a>

Skype for Business on Mac クライアントは、ユニファイド コミュニケーション管理プラットフォーム (UCMP) と、モビリティ クライアントが使用するユニファイド コミュニケーション Web API (UCWA) の両方を活用します。
  
クライアントには、サポートされている構成に Access Edge Server とリバース プロキシが展開されている必要があるという点で、モビリティ クライアントと同じ要件があります。 
  
### <a name="authentication"></a>認証

Skype for Business on Mac クライアントは、展開および有効化時に、Cert ベース認証、Microsoft Modern Authentication、および多要素認証をサポートします。
  
> [!NOTE]
> 現在の制限により、ユーザーの Exchange 資格情報は Skype for Business 資格情報と同じである必要があります。 
  
### <a name="certificates"></a>証明書

Access Edge サーバー、リバース プロキシ サーバー、およびフロント エンド サーバーで使用されている証明書は、SHA-512 ハッシュ アルゴリズムを使用できません。
  
HTTP 証明書失効リストは、クライアントによって定義され、アクセス可能である必要があります。 たとえば、証明書失効リストとして証明書の LDAP エントリはサポートされていません。
  
### <a name="dns"></a>DNS

Mac クライアント上の Skype for Business が正しく機能するには、モビリティを適切に展開する必要があります。 一般的な障害シナリオは、内部ネットワークで次の DNS エントリの両方を解決可能にする場合です。
  
- lyncdiscoverinternal。\<sipdomain\>
    
- lyncdiscover。\<sipdomain\>
    
詳細については [、「Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)でのモビリティの展開」および [「Microsoft Lync Server 2010 Mobility Guide」を参照してください](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>関連項目
<a name="Infrastructure"> </a>

[Skype for Business Server の DNS 要件](../../plan-your-deployment/network-requirements/dns.md)

[よく寄せられる質問](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[既知の問題](https://go.microsoft.com/fwlink/p/?LinkId=798228)