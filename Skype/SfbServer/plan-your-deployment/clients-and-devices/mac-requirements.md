---
title: Skype for Business on Mac クライアントの要件
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
description: このトピックでは、Mac で Skype for Business を実行するためのハードウェア、ソフトウェア、インフラストラクチャの要件について説明します。
ms.openlocfilehash: 08f3aeabbfd88b432c28f05727ec7cf009e297a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803597"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business on Mac クライアントの要件
 
このトピックでは、Mac で Skype for Business を実行するためのハードウェア、ソフトウェア、インフラストラクチャの要件について説明します。
  
[Mac 版 Skype For Business クライアント](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac)は、ダウンロードできます。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac 版 Skype for Business のハードウェアとソフトウェアの要件

Mac 版 Skype for Business クライアントでは、Mac OS X El Capitan 以上が必要です。また、少なくとも100MB のディスク領域を使用します。 すべての内蔵オーディオ デバイスおよび内蔵ビデオ デバイスの使用をサポートしています。 外部デバイスは、 [Skype For Business Solutions カタログ](https://partnersolutions.skypeforbusiness.com/solutionscatalog)に含まれている必要があります。 
  
> [!NOTE]
> このリストは暫定的なものであり、一部のデバイスは Lync 用に認定されていますが、Mac の Skype for Business ではサポートされていません。 必要な最小ハードウェアについては、[システム要件](https://products.office.com/en-us/office-system-requirements)を参照してください。
  
### <a name="legacy-mac-clients"></a>従来の Mac クライアント

Skype for Business Server 2015 は、Mac OS 10.5.8 を実行しているコンピューター、または最新の service pack やリリース (Intel ベース) オペレーティングシステムを実行しているコンピューターでも、次のレガシクライアントをサポートしています (Mac OS 10.9 オペレーティングシステムは現在サポートされていません)。 サポートされる機能の詳細については、「 [Skype For business のデスクトップクライアント機能の比較](desktop-feature-comparison.md)」を参照してください。
  
- Microsoft Lync for Mac 2011 (「 [lync For mac 2011 展開ガイド](https://go.microsoft.com/fwlink/p/?LinkId=268786)」を参照)
    
- Microsoft Communicator for Mac 2011 (「 [communicator For mac 2011 展開ガイド](https://go.microsoft.com/fwlink/p/?LinkId=268787)」を参照)
 
これらのクライアントは、Skype for Business Server 2019 ではサポートされていません。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 版 Skype for Business のインフラストラクチャ要件
<a name="Infrastructure"> </a>

Skype for Business on Mac クライアントでは、ユニファイドコミュニケーション管理プラットフォーム (UCMP) と、モバイルクライアントで使用するユニファイドコミュニケーション Web API (UCMP) の両方が利用されます。
  
クライアントの場合、モバイルクライアントでは、サポートされている構成でアクセスエッジサーバーとリバースプロキシを展開する必要があります。 
  
### <a name="authentication"></a>認証

Mac 版 Skype for Business クライアントは、Cert ベースの認証、Microsoft 先進認証、および展開され有効になっている場合の多要素認証をサポートしています。
  
> [!NOTE]
> 現在の制限のため、ユーザーの Exchange 資格情報は、Skype for Business の資格情報と同じである必要があります。 
  
### <a name="certificates"></a>証明書

アクセス エッジ サーバー、リバース プロキシ サーバー、およびフロント エンド サーバーで使用している証明書では、SHA-512 ハッシュ アルゴリズムは使用しないでください。
  
HTTP 証明書失効リストが定義済みで、クライアントがアクセスできる必要があります。 たとえば、証明書内の LDAP エントリは、証明書失効リストとしてはサポートされません。
  
### <a name="dns"></a>DNS

Mac クライアントの Skype for Business が正常に動作するには、モバイル機能が正しく展開されている必要があります。 失敗する場合の一般的なシナリオは、インターネット ネットワークに次の両方の解決可能な DNS エントリがある場合です。
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
詳細については、「 [Lync server 2013 でのモビリティの展開](https://go.microsoft.com/fwlink/p/?LinkId=798224)と[Microsoft Lync Server 2010 モビリティガイド](https://go.microsoft.com/fwlink//p/?LinkId=798226)」を参照してください。
  
## <a name="see-also"></a>関連項目
<a name="Infrastructure"> </a>

[Skype for Business Server の DNS 要件](../../plan-your-deployment/network-requirements/dns.md)

[よく寄せられる質問](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[既知の問題](https://go.microsoft.com/fwlink/p/?LinkId=798228)
