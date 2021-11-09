---
title: Mac 版 Skype for Business クライアントの要件
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: このトピックでは、Mac でハードウェア、ソフトウェア、およびインフラストラクチャを実行するSkype for Business説明します。
ms.openlocfilehash: b7d3ce484ea3e333e85c2f8473cdcdaaebe44057
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847220"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac 版 Skype for Business クライアントの要件
 
このトピックでは、Mac でハードウェア、ソフトウェア、およびインフラストラクチャを実行するSkype for Business説明します。
  
[Mac クライアントSkype for Businessをダウンロード](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac)できます。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac でのハードウェアとソフトウェアSkype for Business要件

Mac クライアントSkype for Business Mac OS X El Capitan 以上が必要で、少なくとも 100 MB 以上のディスク領域を使用します。 すべての組み込みのオーディオデバイスとビデオ デバイスの使用をサポートしています。 外部デバイスは、デバイスに一[覧表示Microsoft Teams必要があります](https://www.microsoft.com/microsoft-teams/across-devices/devices)。 
  
> [!NOTE]
> このリストは予備的なリストであり、一部のデバイスは Lync の資格を持つ可能性がありますが、Mac 上のSkype for Businessサポートされていません。 必要な最小ハードウェア [については、「System requirements」](https://products.office.com/office-system-requirements) を参照してください。
  
### <a name="legacy-mac-clients"></a>従来の Mac クライアント

Skype for Business Server 2015 では、Mac OS 10.5.8 または最新のサービス パックまたはリリース (Intel ベース) オペレーティング システム (Mac OS 10.9 オペレーティング システムは現在サポートされていません) を実行しているコンピューターで、次の従来のクライアントもサポートしています。 サポートされる機能の詳細については、「デスクトップ クライアント機能の比較」を参照[Skype for Business。](desktop-feature-comparison.md)
  
- Microsoft Lync for Mac 2011 [(「Lync for Mac 2011 Deployment Guide」を参照)](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14))
    
- Microsoft Communicator for Mac 2011 [(「Communicator Mac 2011](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14))展開ガイド」を参照してください)
 
これらのクライアントは、2019 年Skype for Business Serverサポートされていません。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 上のSkype for Businessインフラストラクチャ要件
<a name="Infrastructure"> </a>

Mac Skype for Businessは、ユニファイド コミュニケーション管理プラットフォーム (UCMP) と、モビリティ クライアントが使用するユニファイド コミュニケーション Web API (UCWA) の両方を活用します。
  
クライアントには、サポートされている構成に Access Edge Server とリバース プロキシが展開されている必要があるという点で、モビリティ クライアントと同じ要件があります。 
  
### <a name="authentication"></a>認証

Mac Skype for Businessは、展開および有効化時に、Cert ベース認証、Microsoft Modern Authentication、および多要素認証をサポートします。
  
> [!NOTE]
> 現在の制限により、ユーザーの資格情報はExchange資格情報と同じSkype for Businessがあります。 
  
### <a name="certificates"></a>証明書

Access Edge サーバー、リバース プロキシ サーバー、およびフロント エンド サーバーで使用されている証明書は、SHA-512 ハッシュ アルゴリズムを使用できません。
  
HTTP 証明書失効リストは、クライアントによって定義され、アクセス可能である必要があります。 たとえば、証明書失効リストとして証明書の LDAP エントリはサポートされていません。
  
### <a name="dns"></a>DNS

Mac クライアントで適切に機能するには、Skype for Businessモビリティを適切に展開する必要があります。 一般的な障害シナリオは、内部ネットワークで次の DNS エントリの両方を解決可能にする場合です。
  
- lyncdiscoverinternal。\<sipdomain\>
    
- lyncdiscover。\<sipdomain\>
    
詳細については [、「Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)でのモビリティの展開」および [「Microsoft Lync Server 2010 Mobility Guide」を参照してください](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>関連項目
<a name="Infrastructure"> </a>

[サーバーの DNS 要件Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[よく寄せられる質問](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[既知の問題](https://go.microsoft.com/fwlink/p/?LinkId=798228)