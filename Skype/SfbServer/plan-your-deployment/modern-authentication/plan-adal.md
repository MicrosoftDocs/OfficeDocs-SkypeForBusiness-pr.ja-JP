---
title: Skype for Business で先進認証 (ADAL) を計画する
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
description: この記事では、モダン認証 (Active Directory Authentication Library (ADAL) と OAuth 2.0 に基づく) がどのようなものであるかについて説明します。
ms.openlocfilehash: 239dd6a49ecbec043a661e622a66eb5cb4665e96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815835"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Skype for Business で先進認証 (ADAL) を使用する方法
 
この記事では、Skype for business Server 2015 の2016年3月の累積更新プログラムに含まれている、(Active Directory 認証ライブラリ (ADAL) および OAuth 2.0 に基づく) 先進認証について説明します。または、最初から行うこともできます。Skype for Business Server 2019 のリリース。
  
## <a name="what-is-adal"></a>ADAL とは

ADAL は、'Active Directory Authentication Library (Active Directory 認証ライブラリ)' の頭文字であり、OAuth 2.0 と共に、先進認証の基礎となるものです。 このコードライブラリは、ディレクトリ内のセキュリティで保護されたリソースを、セキュリティトークンを介してクライアントアプリケーション (Skype for Business など) で利用できるようにすることを目的としています。 ADAL は OAuth 2.0 と連携して、多要素認証 (MFA) やさまざまな形式の SAML Auth など、多様な認証および承認シナリオを可能にします。
  
先進認証は、クライアントとして動作するさまざまなアプリがリソースのセキュリティ保護の手段として利用しています。 Skype for Business Server では、このテクノロジをオンプレミスのクライアントとオンプレミスのサーバーの間で使うことで、ユーザーがリソースに適切なレベルの承認を与えることができます。
  
先進認証の通信 (ADAL と OAuth 2.0 をベースに使用) には次のような共通要素があります。
  
- クライアントがリソースに対する要求を行っています。この場合、クライアントは Skype for Business です。
    
- クライアントが特定のレベルのアクセスを必要とするリソースがあります。このリソースは、ディレクトリサービスによって保護されます。この場合、リソースは Skype for Business Server になります。
    
- OAuth 接続 (つまり、ユーザーによるリソースへのアクセスを*許可*する専用の接続) があります。 (OAuth は、"サーバー間の" 認証のわかりやすい名前でも知られています。また、多くの場合、S2S と略記されます)。
    
Skype for Business Server 先進認証 (ADAL) の会話では、Skype for Business Server は ADFS (Windows Server 2012 R2 の ADFS 3.0) 経由で通信します。 認証は、別の ID プロバイダー (IdP) を使用して行うことも可能ですが、Skype for Business Server は、ADFS と直接通信するよう構成する必要があります。 Skype for Business Server で動作するように ADFS を構成していない場合は、 [adfs のインストール](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)を完了してください。
  
ADAL は、Skype for Business Server 2015 の2016年3月の累積更新プログラムに含まれており、Skype for Business の2016年3月の累積更新プログラムをインストールして、正常に**構成するため**に必要です。 Skype for Business Server 2019 の場合は、製品の最初のリリースから入手できます。
  
> [!NOTE]
> 初期のリリースでは、オンプレミス環境での先進認証は、混成の Skype トポロジーが使用されていない場合のみのサポートとなります。 たとえば、環境が純粋な Skype for Business Server の場合などです。 この記述は、変更される可能性があります。 
  
正しい構成には、.ps1 ファイルと ADAL で使用するコマンドが収録された PowerShell パッケージをインストールする必要があります。

Skype for Business で先進認証を実装する方法については、「 [skype For business で先進認証 (ADAL) を使用する方法](../../manage/authentication/use-adal.md)」を参照してください。
