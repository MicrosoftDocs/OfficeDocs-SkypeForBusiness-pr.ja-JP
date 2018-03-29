---
title: Skype for Business Server 2015 のセキュリティ フレームワーク
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: ここでは、Skype のビジネス サーバー 2015 のセキュリティ フレームワークを形成する基本要素の概要を示します。 これらの要素がどのように連携を理解することは、サーバー 2015 のビジネスを展開するための特定、Skype のセキュリティ保護に関する情報に基づいた意思決定を行う必要があります。
ms.openlocfilehash: c29941a3e903b6318db2de0453589b5017e6f51b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="security-framework-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のセキュリティ フレームワーク
 
ここでは、Skype のビジネス サーバー 2015 のセキュリティ フレームワークを形成する基本要素の概要を示します。 これらの要素がどのように連携を理解することは、サーバー 2015 のビジネスを展開するための特定、Skype のセキュリティ保護に関する情報に基づいた意思決定を行う必要があります。
  
具体的な要素は次のとおりです。
  
- Active Directory ドメイン サービス (AD DS) では、ユーザー アカウントとネットワーク リソースの 1 つの信頼されているバックエンド ・ リポジトリを提供します。
    
- 役割ベースのアクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理操作を委任できます。
    
- 公開キー基盤 (PKI) は、信頼された証明機関 (CA) から発行された証明書を使用してサーバーを認証し、データの整合性を確保します。
    
- トランスポート層セキュリティ (TLS)、HTTPS over SSL (HTTPS)、相互 TLS (MTLS) を使用すると、エンドポイント認証と IM の暗号化ができます。ポイント間の音声、ビデオ、アプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。
    
- ユーザーの認証には、業界標準のプロトコルができる限り使用されます。
    
- Windows PowerShell には、ユーザーことはできませんか知らないうちに、簡単にスクリプトを実行するために既定で有効になっているセキュリティ機能が用意されています。
    
確保する基盤をセキュリティで保護された Skype のビジネス サーバー 2015 の信頼されるユーザー、サーバー、接続、および操作を定義するのにはこれらの基本的なセキュリティ要素が連携して動作します。
  
## <a name="in-this-section"></a>このセクションの内容

このセクションのトピックでは、ビジネスのサーバー インフラストラクチャを Skype のセキュリティを強化するためにこれらの基本的な要素の動作方法について説明します。
  
- [ビジネス サーバー 2015 の Skype の active Directory ドメイン サービス](active-directory-domain-services.md)
    
- [ビジネス サーバー 2015 の Skype の役割に基づくアクセス制御 (RBAC)](role-based-access-control-rbac.md)
    
- [ビジネス サーバー 2015 の Skype 用の公開キー基盤](public-key-infrastructure-for-skype.md)
    
- [TLS とビジネス サーバー 2015 の Skype の MTLS](tls-and-mtls.md)
    
- [ビジネス サーバー 2015 の Skype の暗号化](encryption.md)
    
- [ビジネス サーバー 2015 の Skype のユーザーとクライアントの認証](user-and-client-authentication.md)
    
- [Windows PowerShell およびサーバー 2015 のビジネス管理ツールの Skype](management-tools.md)
    

