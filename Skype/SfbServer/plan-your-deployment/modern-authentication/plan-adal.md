---
title: Skype for Business での最新認証 (ADAL) の計画
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
description: この記事では、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づくモダン認証について説明します。
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816227"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Skype for Business でモダン認証 (ADAL) を使用する方法
 
この記事では、2016 年 3 月の Skype for Business for Skype for Business の累積的な更新プログラム (Skype for Business Server 2015) または Skype for Business Server 2019 の最初のリリースにある Active Directory 認証ライブラリ (ADAL) および OAuth 2.0 に基づく) の最新認証について紹介します。
  
## <a name="what-is-adal"></a>ADAL とは

ADAL は 'Active Directory 認証ライブラリ' の頭字語であり、OAuth 2.0 と共に、モダン認証の下支えになります。 このコード ライブラリは、ディレクトリ内のセキュリティで保護されたリソースを、セキュリティ トークンを介してクライアント アプリケーション (Skype for Business など) で使用するように設計されています。 ADAL は OAuth 2.0 と一緒に動作し、多要素認証 (MFA) や SAML 認証のフォームなど、より多くの認証および承認シナリオを有効にします。
  
クライアントとして機能するさまざまなアプリは、セキュリティで保護されたリソースの取得にモダン認証を活用できます。 Skype for Business Server では、このテクノロジは、ユーザーにリソースへの適切なレベルの承認を与えるために、オンプレミスのクライアントとオンプレミス サーバーの間で使用されます。
  
(ADAL と OAuth 2.0 に基づく) 最新の認証の会話には、いくつかの要素が共通しています。
  
- リソースの要求を行うクライアントがいます。この場合、クライアントは Skype for Business です。
    
- クライアントが特定のレベルのアクセスを必要とするリソースが存在し、このリソースはディレクトリ サービスによってセキュリティ保護されます。この場合、リソースは Skype for Business Server です。
    
- つまり、OAuth 接続は、リソースへのアクセスをユーザーに許可する専用の接続です。 (OAuth は、よりわかりやすい名前である "サーバー間" の認証でも知られています。多くの場合、S2S と省略されます)。
    
Skype for Business Server のモダン認証 (ADAL) の会話では、Skype for Business Server は ADFS (ADFS 3.0 Windows Server 2012 R2) を通じて通信します。 認証は他の ID プロバイダー (IdP) を使用して行う場合がありますが、Skype for Business サーバーは ADFS と直接通信するように構成する必要があります。 If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL は、Skype for Business Server 2015 の 2016 年 3 月の累積的な更新プログラムに含まれています。また、Skype for **Business** の 2016 年 3 月の累積的な更新プログラムをインストールする必要があります。また、構成を成功するために必要です。 Skype for Business Server 2019 では、製品の最初のリリースから利用できます。
  
> [!NOTE]
> 最初のリリースでは、Skype トポロジが混在している場合にのみ、オンプレミス環境でのモダン認証がサポートされます。 たとえば、環境が純粋に Skype for Business Server の場合です。 このステートメントは変更される可能性があります。 
  
ADAL で使用されるコマンドを含む .ps1 ファイルを含む PowerShell パッケージは、構成を成功するためにダウンロードする必要があります。

Skype for Business でモダン認証を実装する方法については、「Skype for Business でモダン認証[(ADAL)](../../manage/authentication/use-adal.md)を使用する方法」を参照してください。
