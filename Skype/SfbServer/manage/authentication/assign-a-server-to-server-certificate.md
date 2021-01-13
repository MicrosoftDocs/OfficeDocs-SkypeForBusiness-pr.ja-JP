---
title: Skype for Business Server へのサーバー間認証証明書の割り当て
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
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: '概要: Skype for Business Server のサーバー間認証証明書を割り当てる。'
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828507"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>サーバー間認証証明書を Skype for Business Server に割り当てる
**概要:** Skype for Business Server のサーバー間認証証明書を割り当てる。
  
サーバー間認証証明書が Skype for Business Server に既に割り当てられているかどうかを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

証明書情報が返されな場合は、サーバー間認証を使用する前に、トークン発行者証明書を割り当てる必要があります。 一般に、すべての Skype for Business Server 証明書を OAuthTokenIssuer 証明書として使用できます。たとえば、Skype for Business Server の既定の証明書を OAuthTokenIssuer 証明書として使用することもできます。 (OAUthTokenIssuer 証明書には、[サブジェクト] フィールドに SIP ドメインの名前を含む任意の Web サーバー証明書を指定することもできます)。サーバー間認証に使用する証明書の主な 2 つの要件は次のとおりです。1)すべてのフロントエンド サーバーで同じ証明書を OAuthTokenIssuer 証明書として構成する必要があります。2) 証明書は 2048 ビット以上である必要があります。
  
サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。新しい証明書を要求して取得した後で、フロントエンド サーバーのどれかにログオンし、次のような Windows PowerShell コマンドを使用して証明書をインポートして割り当てます。
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

前のコマンドでは、Path パラメーターは証明書ファイルへの完全なパスを表し、Password パラメーターは証明書に割り当てられたパスワードを表します。 この手順は 1 回だけ実行する必要があります。Skype for Business Server レプリケーション サービスは、すべてのフロントエンド サーバーに証明書を復号化して展開するスケジュールされたタスクのセットを自動的に作成します。
  
または、既存の証明書をサーバー対サーバーの認証の証明書として使用することもできます (前述したように、既定の証明書をサーバー対サーバーの認証の証明書として使用できます)。次の 2 つの Windows PowerShell コマンドを実行すると、既定の証明書の Thumbprint プロパティの値が取得され、その値を使用して、既定の証明書がサーバー対サーバーの認証の証明書として設定されます。
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

上記のコマンドでは、取得した証明書がグローバルなサーバー間認証証明書として機能するように構成されています。つまり、証明書は、すべてのフロントエンド サーバーにレプリケートされ、すべてのフロントエンド サーバーで使用されます。 繰り返しますが、このコマンドは 1 回だけ実行し、フロントエンド サーバーの 1 つでのみ実行する必要があります。 すべてのフロントエンド サーバーで同じ証明書を使用する必要があります。ただし、各フロントエンド サーバーで OAuthTokenIssuer 証明書を構成する必要はありません。 代わりに、証明書を 1 回構成してから、Skype for Business Server レプリケーション サーバーが各サーバーに証明書をコピーします。
  
次Set-CsCertificateは、問題の証明書を取得し、現在の OAuthTokenIssuer 証明書として機能する証明書をすぐに構成します。 (Skype for Business Server は、現在の証明書と以前の証明書の 2 つの証明書の種類のコピーを保持します)。新しい証明書が OAuthTokenIssuer 証明書としてすぐに機能し始める必要がある場合は、次のコマンドレットSet-CsCertificateがあります。
  
Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。 証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。 たとえば、次のコマンドは既定の証明書を取得し、2015 年 7 月 1 日現在の OAuthTokenIssuer 証明書として引き継ぐ証明書を構成します。
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

2015 年 7 月 1 日に、新しい証明書が現在の OAuthTokenIssuer 証明書として構成され、"古い" OAuthTokenIssuer 証明書が以前の証明書として構成されます。
  
Windows PowerShell を使用したくない場合は、証明書 MMC コンソールを使用して 1 台のフロントエンド サーバーから証明書をエクスポートしてから、同じ証明書を他のすべてのフロントエンド サーバーにインポートします。これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。
  
> [!CAUTION]
> この場合、この手順を各フロントエンド サーバーで実行する必要があります。 この方法で証明書をエクスポートおよびインポートする場合、Skype for Business Server は各フロントエンド サーバーに証明書をレプリケートしません。 
  
すべてのフロントエンド サーバーに証明書をインポートした後は、Skype for Business Server 展開ウィザードを使用して証明書を割り当Windows PowerShell。 展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順を実行します。
  
1. [スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server]** をクリックして、[Skype for Business Server 展開ウィザード **] をクリックします**。
    
2. 展開ウィザードで **、[Skype for Business Server システムのインストールまたは更新] をクリックします**。
    
3. [Skype for Business Server]ページで、[ステップ 3: 証明書の要求、インストール、または割り当て] という見出しの下にある [実行]**ボタンをクリックします**。 (注: このコンピューターに証明書が既にインストールされている場合、[実行] ボタンには [再度実行] というラベルが **付きます**)。
    
4. 証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。
    
5. 証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。
    
6. [**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。
    
7. [証明書の割り当ての概要] ページで、[**次へ**] をクリックします。
    
8. [コマンドを実行しています] ページで、[**完了**] をクリックします。
    
9. 証明書ウィザードと展開ウィザードを閉じます。
    

