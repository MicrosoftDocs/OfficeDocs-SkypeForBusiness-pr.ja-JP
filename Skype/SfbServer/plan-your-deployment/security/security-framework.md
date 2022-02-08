---
title: ユーザーのセキュリティ フレームワークSkype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: このセクションでは、セキュリティ フレームワークを形成する基本的な要素の概要をSkype for Business Server。 これらの要素がどのように組み合わせて機能するのか理解は、特定の展開環境のセキュリティ保護に関する情報に基づいた意思決定を行Skype for Business Serverです。
ms.openlocfilehash: 927b51fca298d665e45597d943bbb8cbd3e2a2ac
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394969"
---
# <a name="security-framework-for-skype-for-business-server"></a>ユーザーのセキュリティ フレームワークSkype for Business Server
 
このセクションでは、セキュリティ フレームワークを形成する基本的な要素の概要をSkype for Business Server。 これらの要素がどのように組み合わせて機能するのか理解は、特定の展開環境のセキュリティ保護に関する情報に基づいた意思決定を行Skype for Business Serverです。
  
具体的な要素は次のとおりです。
  
- Active Directory ドメイン サービス (AD DS) は、ユーザー アカウントとネットワーク リソースの信頼できる単一のバックエンド リポジトリを提供します。
    
- Role-Basedアクセス制御 (RBAC) を使用すると、高いセキュリティ基準を維持しながら管理タスクを委任できます。
    
- 公開キーインフラストラクチャ (PKI) は、信頼できる証明機関 (CA) によって発行された証明書を使用してサーバーを認証し、データの整合性を確保します。
    
- トランスポート層セキュリティ (TLS)、HTTP over SSL (HTTPS)、および相互 TLS (MTLS) により、エンドポイント認証と IM の暗号化が可能になります。ポイント間の音声、ビデオ、およびアプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。
    
- ユーザーの認証には、業界標準のプロトコルが可能な限り使用されます。
    
- Windows PowerShell には、既定で有効となっているセキュリティ機能があり、ユーザーが簡単には (または知らないうちに) スクリプトを実行できないようになっています。
    
これらの基本的なセキュリティ要素を組み合わせて、信頼できるユーザー、サーバー、接続、および操作を定義し、セキュリティで保護されたセキュリティ基盤をSkype for Business Server。
  
## <a name="in-this-section"></a>このセクションの内容

このセクションのトピックでは、これらの基本的な各要素が、インフラストラクチャのセキュリティを強化するためにどのように機能Skype for Business Serverします。
  
- [Active Directory ドメイン サービス for Skype for Business Server](active-directory-domain-services.md)
    
- [ユーザーの役割ベースのアクセス制御 (RBAC) Skype for Business Server](role-based-access-control-rbac.md)
    
- [パブリック キー インフラストラクチャ Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS および MTLS for Skype for Business Server](tls-and-mtls.md)
    
- [ユーザーの暗号化Skype for Business Server](encryption.md)
    
- [ユーザーとクライアントの認証Skype for Business Server](user-and-client-authentication.md)
    
- [Windows PowerShellおよびSkype for Business Server管理ツール](management-tools.md)
    

