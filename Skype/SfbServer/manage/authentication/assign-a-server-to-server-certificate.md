---
title: サーバー間認証証明書をサーバー間認証証明書に割り当Skype for Business Server
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
description: '概要: サーバー間認証証明書をサーバー間認証証明書に割り当Skype for Business Server。'
ms.openlocfilehash: b3d662dc3d0e18f0aefd1d8e643e09554fc39d652d31ac0bf8ed5540a5e34d8f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338155"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>サーバー間認証証明書をサーバー間認証証明書に割り当Skype for Business Server
**概要:** サーバー間認証証明書を割り当Skype for Business Server。
  
サーバー間認証証明書が既に Skype for Business Server に割り当てられているかどうかを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

証明書情報が返されない場合は、サーバー間認証を使用する前にトークン発行者証明書を割り当てる必要があります。 一般的なルールとして、すべてのSkype for Business Server OAuthTokenIssuer 証明書として使用できます。たとえば、既定Skype for Business Server OAuthTokenIssuer 証明書として使用できます。 (OAUthTokenIssuer 証明書には、[サブジェクト] フィールドに SIP ドメインの名前を含む Web サーバー証明書を指定することもできます)。サーバー間認証に使用される証明書の主な 2 つの要件は次のとおりです。1)すべてのフロントエンド サーバーで同じ証明書を OAuthTokenIssuer 証明書として構成する必要があります。2) 証明書は少なくとも 2048 ビットである必要があります。
  
サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。新しい証明書を要求して取得した後で、フロントエンド サーバーのどれかにログオンし、次のような Windows PowerShell コマンドを使用して証明書をインポートして割り当てます。
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

前のコマンドでは、Path パラメーターは証明書ファイルへの完全なパスを表し、Password パラメーターは証明書に割り当てられたパスワードを表します。 この手順は 1 回だけ実行する必要があります。Skype for Business Server レプリケーション サービスは、すべてのフロントエンド サーバーに証明書を復号化して展開する一連のスケジュールされたタスクを自動的に作成します。
  
または、既存の証明書をサーバー対サーバーの認証の証明書として使用することもできます (前述したように、既定の証明書をサーバー対サーバーの認証の証明書として使用できます)。次の 2 つの Windows PowerShell コマンドを実行すると、既定の証明書の Thumbprint プロパティの値が取得され、その値を使用して、既定の証明書がサーバー対サーバーの認証の証明書として設定されます。
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

前のコマンドでは、取得された証明書がグローバル サーバー間認証証明書として機能するように構成されています。つまり、証明書は、すべてのフロントエンド サーバーにレプリケートされ、使用されます。 繰り返しますが、このコマンドは 1 回だけ実行し、フロント エンド サーバーの 1 つでのみ実行する必要があります。 すべてのフロントエンド サーバーで同じ証明書を使用する必要があります。ただし、各フロントエンド サーバーで OAuthTokenIssuer 証明書を構成する必要はありません。 代わりに、証明書を 1 回構成してから、Skype for Business Serverサーバーが各サーバーに証明書をコピーする操作を行います。
  
このSet-CsCertificateは、問題の証明書を受け取り、その証明書が現在の OAuthTokenIssuer 証明書として機能するためにすぐに構成されます。 (Skype for Business Serverは、現在の証明書と以前の証明書の 2 つのコピーを保持します。新しい証明書が OAuthTokenIssuer 証明書としてすぐに機能し始める必要がある場合は、次のコマンドレットをSet-CsCertificateします。
  
Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。 証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。 たとえば、このコマンドは既定の証明書を取得し、2015 年 7 月 1 日現在の OAuthTokenIssuer 証明書として引き継ぐ証明書を構成します。
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

2015 年 7 月 1 日に、新しい証明書が現在の OAuthTokenIssuer 証明書として構成され、"古い" OAuthTokenIssuer 証明書が以前の証明書として構成されます。
  
Windows PowerShell を使用したくない場合は、証明書 MMC コンソールを使用して 1 台のフロントエンド サーバーから証明書をエクスポートしてから、同じ証明書を他のすべてのフロントエンド サーバーにインポートします。これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。
  
> [!CAUTION]
> この場合、この手順を各フロントエンド サーバーで実行する必要があります。 この方法で証明書をエクスポートおよびインポートする場合Skype for Business Server、その証明書を各フロントエンド サーバーにレプリケートしません。 
  
すべてのフロントエンド サーバーに証明書をインポートした後、その証明書を割り当てるには、証明書の代わりに Skype for Business Server 展開ウィザードをWindows PowerShell。 展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順を実行します。
  
1. [スタート] ボタン、[すべてのプログラム] をクリックし、[Skype for Business Server]**をクリック** し、[展開 **ウィザードSkype for Business Serverクリックします**。
    
2. 展開ウィザードで、[システムのインストールまたは **更新] をSkype for Business Serverします**。
    
3. [証明書のSkype for Business Server] ページで、[手順3: 証明書の要求、インストール、または割り当て] という見出しの下にある [実行]**ボタンをクリックします**。 (注: このコンピューターに既に証明書をインストールしている場合は、[ **実行** ] ボタンに [もう一度実行する] という **ラベルが付きます**)。
    
4. 証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。
    
5. 証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。
    
6. [**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。
    
7. [証明書の割り当ての概要] ページで、[**次へ**] をクリックします。
    
8. [コマンドを実行しています] ページで、[**完了**] をクリックします。
    
9. 証明書ウィザードと展開ウィザードを閉じます。
    

