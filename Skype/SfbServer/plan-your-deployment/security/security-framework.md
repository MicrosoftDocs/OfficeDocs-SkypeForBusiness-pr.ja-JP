---
title: Skype for Business Server のセキュリティフレームワーク
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: このセクションでは、Skype for Business Server のセキュリティフレームワークを形成する基本的な要素の概要について説明します。 これらの要素がどのように連携するかを理解することは、特定の Skype for Business Server の展開をセキュリティで保護することに関する意思決定を行うために不可欠です。
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296876"
---
# <a name="security-framework-for-skype-for-business-server"></a>Skype for Business Server のセキュリティフレームワーク
 
このセクションでは、Skype for Business Server のセキュリティフレームワークを形成する基本的な要素の概要について説明します。 これらの要素がどのように連携するかを理解することは、特定の Skype for Business Server の展開をセキュリティで保護することに関する意思決定を行うために不可欠です。
  
具体的な要素は次のとおりです。
  
- Active Directory ドメインサービス (AD DS) は、ユーザーアカウントとネットワークリソース用の1つの信頼されたバックエンドリポジトリを提供します。
    
- 役割ベースのアクセス制御 (RBAC) を使用すると、高水準のセキュリティを維持しながら管理操作を委任できます。
    
- 公開キー基盤 (PKI) は、信頼された証明機関 (CA) から発行された証明書を使用してサーバーを認証し、データの整合性を確保します。
    
- トランスポート層セキュリティ (TLS)、HTTPS over SSL (HTTPS)、相互 TLS (MTLS) を使用すると、エンドポイント認証と IM の暗号化ができます。ポイント間の音声、ビデオ、アプリケーション共有のストリームは、セキュア リアルタイム転送プロトコル (SRTP) で暗号化されます。
    
- ユーザーの認証には、業界標準のプロトコルができる限り使用されます。
    
- Windows PowerShell には既定で有効になっているセキュリティ機能が用意されているため、ユーザーは簡単にスクリプトを実行することはできません。
    
これらの基本的なセキュリティ要素は連携して、Skype for Business Server のセキュリティ保護された基盤を確保するのに役立つ、信頼されたユーザー、サーバー、接続、操作を定義します。
  
## <a name="in-this-section"></a>このセクションの内容

このセクションのトピックでは、Skype for Business Server インフラストラクチャのセキュリティを強化するために、これらの各基本的な要素がどのように動作するかについて説明します。
  
- [Skype for Business Server の Active Directory ドメインサービス](active-directory-domain-services.md)
    
- [Skype for Business Server の役割ベースのアクセス制御 (RBAC)](role-based-access-control-rbac.md)
    
- [Skype for Business Server の公開キー基盤](public-key-infrastructure-for-skype.md)
    
- [Skype for Business Server の TLS と MTLS](tls-and-mtls.md)
    
- [Skype for Business Server の暗号化](encryption.md)
    
- [Skype for Business Server のユーザーとクライアントの認証](user-and-client-authentication.md)
    
- [Windows PowerShell と Skype for Business Server 管理ツール](management-tools.md)
    

