---
title: 現代での認証 (ADAL) Skype ビジネスの計画
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: この資料では、どのような近代的な認証、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) はについて説明します。
ms.openlocfilehash: 0c3aeef2480494e45a4d18589b3e3cdc6d9c5357
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213908"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Skype for Business で先進認証 (ADAL) を使用する方法
 
この記事で紹介現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているビジネス サーバー 2015 年または最初から、Skype のビジネス用の Skype 用の累積的な更新ビジネス サーバー 2019 の Skype をリリースします。
  
## <a name="what-is-adal"></a>ADAL とは

ADAL は、'Active Directory Authentication Library (Active Directory 認証ライブラリ)' の頭文字であり、OAuth 2.0 と共に、先進認証の基礎となるものです。 このコード ライブラリは、(ビジネス用の Skype) のようなセキュリティ トークンを使用してクライアント ・ アプリケーションに利用可能なディレクトリにセキュリティで保護されたリソースを作成するよう設計されています。 ADAL は OAuth 2.0 と連携して、多要素認証 (MFA) やさまざまな形式の SAML Auth など、多様な認証および承認シナリオを可能にします。
  
先進認証は、クライアントとして動作するさまざまなアプリがリソースのセキュリティ保護の手段として利用しています。 ビジネス サーバーの Skype は、オンプレミスのクライアントとオンプレミスのサーバー間でユーザーにリソースへの承認の適切なレベルを提供するためにこの技術を使用します。
  
先進認証の通信 (ADAL と OAuth 2.0 をベースに使用) には次のような共通要素があります。
  
- リソースの要求を行うクライアントが、この場合、クライアントは、ビジネスの Skype です。
    
- クライアントが特定のレベルのアクセスを必要とするリソースがある、ディレクトリ サービスがこのリソースがセキュリティで保護されたリソースのビジネス サーバー用の Skype はここで。
    
- OAuth の接続、つまり、他の接続がリソースにアクセスするユーザーを*承認*するのには専用です。 (OAuth は 'サーバー' への認証に、わかりやすい名前で知られています、S2S と省略は、多くの場合)。
    
ビジネス サーバー ・最新認証 (ADAL) 会話の Skype、Skype ビジネス サーバーの ADFS (Windows Server 2012 R2 の ad FS 3.0) を介して通信します。 認証は、別の ID プロバイダー (IdP) を使用して行うことも可能ですが、Skype for Business Server は、ADFS と直接通信するよう構成する必要があります。 ビジネス サーバーの Skype 上で動作する ADFS を構成していない場合は、 [ad FS のインストール](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)を完了してください。
  
ADAL は、2016年 3 月に含まれているビジネス サーバー 2015 年の Skype 用の累積的な更新および年 2016年 3 月のビジネスの**必要があります**Skype の累積的な更新プログラムをインストールし、正しい構成のために必要な。 ビジネス サーバー 2019 の Skype は、製品の初期リリースから利用可能です。
  
> [!NOTE]
> 初期のリリースでは、オンプレミス環境での先進認証は、混成の Skype トポロジーが使用されていない場合のみのサポートとなります。 環境がビジネス サーバーの Skype では純粋である場合などです。 この記述は、変更される可能性があります。 
  
正しい構成には、.ps1 ファイルと ADAL で使用するコマンドが収録された PowerShell パッケージをインストールする必要があります。

ビジネス用の Skype の最新の認証を実装する方法についてを参照してください:[ビジネス用の Skype で最新の認証 (ADAL) を使用する方法](../../manage/authentication/use-adal.md)
