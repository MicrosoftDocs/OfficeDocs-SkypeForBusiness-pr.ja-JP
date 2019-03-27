---
title: Skype ビジネス サーバー用のセキュリティ フレームワーク
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: このセクションでは、Skype のビジネス サーバーのセキュリティ フレームワークを形成する基本的な要素の概要を提供します。 これらの要素がどのように連携を理解することは、ビジネス サーバーの展開についての特定、Skype のセキュリティ保護に関する情報に基づいた決定を行う必要があります。
ms.openlocfilehash: 7c678e1f005178b569f8e4136d40fd911483a3d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879883"
---
# <a name="security-framework-for-skype-for-business-server"></a>Skype ビジネス サーバー用のセキュリティ フレームワーク
 
このセクションでは、Skype のビジネス サーバーのセキュリティ フレームワークを形成する基本的な要素の概要を提供します。 これらの要素がどのように連携を理解することは、ビジネス サーバーの展開についての特定、Skype のセキュリティ保護に関する情報に基づいた決定を行う必要があります。
  
具体的な要素は次のとおりです。
  
- Active Directory ドメイン サービス (AD DS) では、ユーザー アカウントとネットワーク リソースの 1 つの信頼されているバックエンド ・ リポジトリを提供します。
    
- 役割ベースのアクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理操作を委任できます。
    
- 公開キー基盤 (PKI) は、信頼された証明機関 (CA) から発行された証明書を使用してサーバーを認証し、データの整合性を確保します。
    
- トランスポート層セキュリティ (TLS)、HTTPS over SSL (HTTPS)、相互 TLS (MTLS) を使用すると、エンドポイント認証と IM の暗号化ができます。ポイント間の音声、ビデオ、アプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。
    
- ユーザーの認証には、業界標準のプロトコルができる限り使用されます。
    
- Windows PowerShell には、ユーザーことはできませんか知らないうちに、簡単にスクリプトを実行するために既定で有効になっているセキュリティ機能が用意されています。
    
Skype のビジネス サーバーのセキュリティで保護された基盤を確実に信頼できるユーザー、サーバー、接続、および操作を定義するのにはこれらの基本的なセキュリティ要素が連携して動作します。
  
## <a name="in-this-section"></a>このセクションの内容

このセクションのトピックでは、ビジネスのサーバー インフラストラクチャを Skype のセキュリティを強化するためにこれらの基本的な要素の動作方法について説明します。
  
- [Skype ビジネス サーバーの active Directory ドメイン サービス](active-directory-domain-services.md)
    
- [Skype ビジネス サーバーの役割に基づくアクセス制御 (RBAC)](role-based-access-control-rbac.md)
    
- [Skype ビジネス サーバーのための公開キー基盤](public-key-infrastructure-for-skype.md)
    
- [TLS と Skype ビジネス サーバー用の MTLS](tls-and-mtls.md)
    
- [Skype のビジネス サーバー用の暗号化](encryption.md)
    
- [ビジネス サーバーの Skype のユーザーとクライアントの認証](user-and-client-authentication.md)
    
- [Windows PowerShell と Skype ビジネス サーバー管理ツールの](management-tools.md)
    

