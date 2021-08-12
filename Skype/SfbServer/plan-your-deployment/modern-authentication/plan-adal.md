---
title: 最新の認証 (ADAL) の計画とSkype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: この記事では、モダン認証 (Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) について説明します。
ms.openlocfilehash: 317c899600730438a56dc3e52ddf76ce5eeb6d6da5297ab2732166ceb9880074
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349919"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>モダン認証 (ADAL) とパスワードを使用するSkype for Business
 
この記事では、Skype for Business Server 2015 の 2016 年 3 月の累積的な更新プログラム (Skype for Business の Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく)、または Skype for Business Server 2019 の初期リリースから、モダン認証について紹介します。
  
## <a name="what-is-adal"></a>ADAL とは

ADAL は 'Active Directory 認証ライブラリ' の頭字語であり、OAuth 2.0 と共に、モダン認証の下支えです。 このコード ライブラリは、ディレクトリ内のセキュリティで保護されたリソースを、セキュリティ トークンを介して (Skype for Business など) クライアント アプリケーションで使用するように設計されています。 ADAL は OAuth 2.0 と機能し、多要素認証 (MFA) などのより多くの認証および承認シナリオや、より多くの形式の SAML Auth を有効にします。
  
クライアントとして機能するさまざまなアプリは、セキュリティで保護されたリソースの取得に役立つモダン認証を活用できます。 このSkype for Business Server、このテクノロジは、ユーザーにリソースに対する適切なレベルの承認を与えるために、オンプレミス のクライアントとオンプレミス サーバーの間で使用されます。
  
最新の認証の会話 (ADAL と OAuth 2.0 に基づく) には、共通する要素があります。
  
- リソースの要求を行うクライアントがいます。この場合、クライアントはSkype for Business。
    
- クライアントが特定のレベルのアクセスを必要とするリソースが存在し、このリソースはディレクトリ サービスによってセキュリティ保護されます(この場合、リソースはSkype for Business Server。
    
- つまり、ユーザーにリソースへのアクセスを許可する専用の接続である OAuth接続があります。 (OAuth は、"Server-to-Server" 認証というわかりやすい名前でも知られています。多くの場合、S2S と省略されます)。
    
モダンSkype for Business Server (ADAL) 会話では、Skype for Business Server ADFS (ADFS 3.0 in Windows Server 2012 R2) を介して通信します。 認証は他の ID プロバイダー (IdP) を使用して行う場合がありますが、Skype for Businessサーバーが ADFS と直接通信するように構成する必要があります。 ADFS を構成していない場合は、ADFS Skype for Business Server[を完了してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。
  
ADAL は 2015 年 3 月の Skype for Business Server 2016 年 3 月の累積的な更新プログラムに含まれており、Skype for Business の 2016 年 **3** 月の累積的な更新プログラムをインストールする必要があります。 2019 Skype for Business Server、製品の最初のリリースから利用できます。
  
> [!NOTE]
> 最初のリリースでは、オンプレミス環境でのモダン認証がサポートされるのは、関連するトポロジに混在Skype場合のみです。 たとえば、環境が純粋に使用されている場合Skype for Business Server。 このステートメントは変更される可能性があります。 
  
ADAL で使用されるコマンド.ps1ファイルを含む PowerShell パッケージをダウンロードして、構成を成功する必要があります。

最新の認証を Skype for Business で実装する方法については、「モダン認証[(ADAL)](/microsoft-365/enterprise/hybrid-modern-auth-overview)を使用する方法」を参照Skype for Business