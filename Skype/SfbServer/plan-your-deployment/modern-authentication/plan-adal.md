---
title: Skype for Business でのモダン認証 (ADAL) の計画
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
ms.openlocfilehash: 1df07491881b90efc16c97e7cd5cec0953cfb346
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096613"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Skype for Business でモダン認証 (ADAL) を使用する方法
 
この記事では、Skype for Business Server 2015 の Skype for Business の 2016 年 3 月の累積的な更新プログラム、または Skype for Business Server 2019 の初期リリースから見つかったモダン認証 (Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) について紹介します。
  
## <a name="what-is-adal"></a>ADAL とは

ADAL は 'Active Directory 認証ライブラリ' の頭字語であり、OAuth 2.0 と共に、モダン認証の下支えです。 このコード ライブラリは、ディレクトリ内のセキュリティで保護されたリソースを、セキュリティ トークンを介してクライアント アプリケーション (Skype for Business など) で利用するように設計されています。 ADAL は OAuth 2.0 と機能し、多要素認証 (MFA) などのより多くの認証および承認シナリオや、より多くの形式の SAML Auth を有効にします。
  
クライアントとして機能するさまざまなアプリは、セキュリティで保護されたリソースの取得に役立つモダン認証を活用できます。 Skype for Business Server では、このテクノロジは、ユーザーにリソースに対する適切なレベルの承認を与えるために、オンプレミス のクライアントとオンプレミス サーバーの間で使用されます。
  
最新の認証の会話 (ADAL と OAuth 2.0 に基づく) には、共通する要素があります。
  
- リソースの要求を行うクライアントがあります。この場合、クライアントは Skype for Business です。
    
- クライアントが特定のレベルのアクセスを必要とするリソースが存在し、このリソースはディレクトリ サービスによってセキュリティ保護されます。この場合、リソースは Skype for Business Server です。
    
- つまり、ユーザーにリソースへのアクセスを許可する専用の接続である OAuth接続があります。 (OAuth は、"Server-to-Server" 認証というわかりやすい名前でも知られています。多くの場合、S2S と省略されます)。
    
Skype for Business Server Modern Authentication (ADAL) の会話では、Skype for Business Server は ADFS (ADFS 3.0 in Windows Server 2012 R2) を介して通信します。 認証は、他の ID プロバイダー (IdP) を使用して行う場合がありますが、Skype for Business サーバーは、ADFS と直接通信するように構成する必要があります。 Skype for Business Server で動作するように ADFS を構成していない場合は [、ADFS のインストールを完了してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。
  
ADAL は、Skype for Business Server 2015 の 2016 年 3 月の累積的な更新プログラムに含まれており、Skype for **Business** の 2016 年 3 月の累積的な更新プログラムをインストールする必要があります。 Skype for Business Server 2019 では、製品の最初のリリースから利用できます。
  
> [!NOTE]
> 最初のリリースでは、Skype トポロジが混在している場合にのみ、オンプレミス環境でのモダン認証がサポートされます。 たとえば、環境が純粋に Skype for Business Server の場合です。 このステートメントは変更される可能性があります。 
  
ADAL で使用されるコマンドを含む .ps1 ファイルを含む PowerShell パッケージをダウンロードして、構成を成功する必要があります。

Skype for Business でモダン認証を実装する方法については、「Skype for Business でモダン認証 [(ADAL) を使用する方法」を参照してください。](/microsoft-365/enterprise/hybrid-modern-auth-overview)