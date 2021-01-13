---
title: Skype for Business Server のセキュリティ フレームワーク
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
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: このセクションでは、Skype for Business Server のセキュリティ フレームワークを形成する基本的な要素の概要について説明します。 これらの要素がどのように機能し合うのかは、特定の Skype for Business Server 展開のセキュリティ保護に関する情報に基づいた決定を行う上で不可欠です。
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832097"
---
# <a name="security-framework-for-skype-for-business-server"></a>Skype for Business Server のセキュリティ フレームワーク
 
このセクションでは、Skype for Business Server のセキュリティ フレームワークを形成する基本的な要素の概要について説明します。 これらの要素がどのように組み合うのか理解は、特定の Skype for Business Server 展開をセキュリティで保護するための情報に基づいた決定を行う上で不可欠です。
  
具体的な要素は次のとおりです。
  
- Active Directory ドメイン サービス (AD DS) は、ユーザー アカウントとネットワーク リソースの信頼できる単一のバックエンド リポジトリを提供します。
    
- Role-Based (RBAC) を使用すると、高レベルのセキュリティを維持しながら管理タスクを委任できます。
    
- 公開キー基盤 (PKI) は、信頼された証明機関 (CA) によって発行された証明書を使用して、サーバーを認証し、データの整合性を確保します。
    
- トランスポート層セキュリティ (TLS)、HTTP over SSL (HTTPS)、および相互 TLS (MTLS) により、エンドポイント認証と IM の暗号化が可能になります。ポイント間の音声、ビデオ、およびアプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。
    
- ユーザーの認証には、業界標準のプロトコルが可能な限り使用されます。
    
- Windows PowerShell には、既定で有効となっているセキュリティ機能があり、ユーザーが簡単には (または知らないうちに) スクリプトを実行できないようになっています。
    
これらの基本的なセキュリティ要素は、信頼できるユーザー、サーバー、接続、および操作を定義して、Skype for Business Server のセキュリティで保護された基盤を確保するために機能します。
  
## <a name="in-this-section"></a>このセクションの内容

このセクションのトピックでは、Skype for Business Server インフラストラクチャのセキュリティを強化するために、これらの各基本要素がどのように機能するのかについて説明します。
  
- [Skype for Business Server の Active Directory ドメイン サービス](active-directory-domain-services.md)
    
- [Skype for Business Server の役割ベースのアクセス制御 (RBAC)](role-based-access-control-rbac.md)
    
- [Skype for Business Server の公開キー基盤](public-key-infrastructure-for-skype.md)
    
- [Skype for Business Server の TLS と MTLS](tls-and-mtls.md)
    
- [Skype for Business Server の暗号化](encryption.md)
    
- [Skype for Business Server のユーザー認証とクライアント認証](user-and-client-authentication.md)
    
- [Windows PowerShell Skype for Business Server 管理ツール](management-tools.md)
    

