---
title: Skype for Business での先進認証 (ADAL) の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: この記事では、モダン認証 (Active Directory 認証ライブラリ (ADAL) および OAuth 2.0 に基づく) がどのようなものかについて説明します。
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046290"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Skype for Business での先進認証 (ADAL) の使用方法
 
この記事では、(Active Directory 認証ライブラリ (ADAL) および OAuth 2.0 を基にした) モダン認証 (skype for business Server 2015 の Skype for business の累積的な更新プログラム2016、または初期から入手可能) について説明します。Skype for Business Server 2019 のリリース。
  
## <a name="what-is-adal"></a>ADAL とは

ADAL は、「Active Directory 認証ライブラリ」の頭字語であり、OAuth 2.0 とともに、先進認証の underpinning です。 このコードライブラリは、ディレクトリ内のセキュリティで保護されたリソースをセキュリティトークンを介してクライアントアプリケーション (Skype for Business など) で使用できるようにするためのものです。 ADAL は OAuth 2.0 と連携して、多要素認証 (MFA) やその他の形式の SAML 認証など、より多くの認証と承認のシナリオを可能にします。
  
クライアントとして機能するさまざまなアプリは、セキュリティで保護されたリソースへの取得を支援する先進認証を活用することができます。 Skype for Business Server では、ユーザーがリソースに対して適切なレベルの承認を得るために、このテクノロジがオンプレミスのクライアントとオンプレミスのサーバーの間で使用されます。
  
モダン認証の会話 (ADAL と OAuth 2.0 に基づく) には、いくつかの要素が共通しています。
  
- クライアントがリソースに対して要求を発行しています。この場合、クライアントは Skype for Business です。
    
- クライアントが特定のレベルのアクセスを必要とするリソースがあり、このリソースはディレクトリサービスによって保護されています。この場合、リソースは Skype for Business Server です。
    
- その他に、OAuth 接続 (つまり、リソースへのアクセスをユーザーに*許可する専用*の接続) があります。 (OAuth は、よりわかりやすい名前 ' ' サーバー間 ' auth によっても知られており、多くの場合、S2S と略記されます。)
    
Skype for Business Server モダン認証 (ADAL) 会話では、Skype for Business Server は ADFS (Windows Server 2012 R2 の ADFS 3.0) を介して通信します。 認証は他の Id プロバイダー (IdP) を使用して行われることがありますが、Skype for Business server を ADFS と直接通信するように構成する必要があります。 Skype for Business Server と連携するように ADFS を構成していない場合は、 [adfs のインストール](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)を完了してください。
  
ADAL は、Skype for business Server 2015 用の2016年3月の累積的な更新プログラムに含まれています。また、構成を正常に行うには、Skype for business の累積的な更新プログラムの2016年3月をインストールする**必要があり**ます。 Skype for Business Server 2019 の場合は、製品の初期リリースから入手できます。
  
> [!NOTE]
> 最初のリリースでは、オンプレミス環境での先進認証がサポートされるのは、混合 Skype トポロジが関係しない場合のみです。 たとえば、環境が純粋に Skype for Business Server の場合などです。 このステートメントは変更される可能性があります。 
  
ADAL で使用されるコマンドを含む、ps1 ファイルを含む PowerShell パッケージは、正常な構成のためにダウンロードする必要があります。

Skype for business で先進認証を実装する方法については、「 [skype For business で先進認証 (ADAL) を使用する方法](../../manage/authentication/use-adal.md)」を参照してください。
