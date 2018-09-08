---
title: Mac クライアントの要件にビジネス用の Skype
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: ハードウェア、ソフトウェア、およびビジネス用の Skype を実行して、mac 上のインフラストラクチャの要件の詳細については、このトピックを読む
ms.openlocfilehash: 184f94dfb272ce2160667d31825309001ab8396d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886379"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac クライアントの要件にビジネス用の Skype
 
ハードウェア、ソフトウェア、およびビジネス用の Skype を実行して、mac 上のインフラストラクチャの要件の詳細については、このトピックを読む
  
[Mac クライアントのビジネス用の Skype](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac)は、ダウンロード可能です。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Mac での Skype for Business のハードウェア要件およびソフトウェア要件

Mac クライアントのビジネスの Skype では、Mac OS X 許可されて、それ以上を必要とし、少なくとも 100 MB のディスク領域を使用します。 すべての内蔵オーディオ デバイスおよび内蔵ビデオ デバイスの使用をサポートしています。 外付けデバイスは、 [Skype](https://partnersolutions.skypeforbusiness.com/solutionscatalog)でなければなりません。 
  
> [!NOTE]
> このリストは暫定版と一部のデバイスを Lync では、認定されたことがありますが、mac でのビジネス用の Skype ではサポートされません。 必要なハードウェアの最小の[システム要件](https://products.office.com/en-us/office-system-requirements)を参照してください。
  
### <a name="legacy-mac-clients"></a>従来の Mac クライアント

ビジネス サーバー 2015 の Skype では、Mac OS 10.5.8 または最新の service pack を実行しているか (Intel ベース) オペレーティング システム (Mac OS 10.9 オペレーティング システムは現在サポートされていません) を解放するコンピューターで次のレガシ クライアントもサポートします。 詳細については、サポートされている機能は、[ビジネスの Skype のデスクトップ クライアントの機能の比較](desktop-feature-comparison.md)を参照してください。
  
- マイクロソフトの Lync for Mac 2011 の ( [Lync](https://go.microsoft.com/fwlink/p/?LinkId=268786)を参照してください)
    
- マイクロソフトの Communicator for Mac 2011 ( [Communicator for Mac 2011 の 『 導入ガイド 』](https://go.microsoft.com/fwlink/p/?LinkId=268787)を参照してください)
 
ビジネス サーバー 2019 の Skype によって、これらのクライアントがサポートされていません。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Mac 上の Skype for Business インフラストラクチャー要件
<a name="Infrastructure"> </a>

Mac クライアントのビジネス用の Skype は、ユニファイド コミュニケーション Web API (UCWA)、モビリティ クライアントを使用するだけでなく、ユニファイド コミュニケーション管理プラットフォーム (UCMP) を活用します。
  
クライアントでは、アクセス エッジ サーバーがある必要があり、リバース プロキシがサポートされている構成に展開する、モバイル クライアントと同様の要件があります。 
  
### <a name="authentication"></a>認証

Mac クライアントのビジネスの Skype では、証明書ベースの認証、マイクロソフト現代認証、および展開し、有効にしたとき、多元的な認証をサポートします。
  
> [!NOTE]
> 現在の制限のためは、ユーザーの Exchange の資格情報はビジネスの資格情報は、Skype と同じである必要があります。 
  
### <a name="certificates"></a>証明書

アクセス エッジ サーバー、リバース プロキシ サーバー、およびフロント エンド サーバーで使用している証明書では、SHA-512 ハッシュ アルゴリズムは使用しないでください。
  
HTTP 証明書失効リストが定義済みで、クライアントがアクセスできる必要があります。 などをサポートしていません LDAP エントリの証明書、証明書失効リストとして。
  
### <a name="dns"></a>DNS

モビリティは、適切に動作する Mac クライアントのビジネスの Skype の正しく展開する必要があります。 失敗する場合の一般的なシナリオは、インターネット ネットワークに次の両方の解決可能な DNS エントリがある場合です。
  
- lyncdiscoverinternal。\<sipdomain\>
    
- lyncdiscover。\<sipdomain\>
    
詳細についてを参照してください: [Lync Server 2013 でのモビリティの展開](https://go.microsoft.com/fwlink/p/?LinkId=798224)、および[Microsoft Lync Server 2010 モビリティのガイド](https://go.microsoft.com/fwlink//p/?LinkId=798226)です。
  
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="Infrastructure"> </a>

[Skype のビジネス サーバー用の DNS の要件](../../plan-your-deployment/network-requirements/dns.md)

[よく寄せられる質問](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[既知の問題](https://go.microsoft.com/fwlink/p/?LinkId=798228)