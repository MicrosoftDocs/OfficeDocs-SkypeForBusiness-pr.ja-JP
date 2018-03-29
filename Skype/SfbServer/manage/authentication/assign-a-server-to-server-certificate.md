---
title: サーバー間の認証証明書を Skype for Business Server 2015 に割り当てる
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: '概要: ビジネス サーバー 2015 の Skype のサーバーのサーバー認証証明書を割り当てます。'
ms.openlocfilehash: 7bc697d9c45b55708ffb3fa20f04fbeb3eec9de9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server-2015"></a>サーバー間の認証証明書を Skype for Business Server 2015 に割り当てる
**の概要:**ビジネス サーバー 2015 の Skype のサーバーのサーバー認証証明書を割り当てます。
  
確認するかどうかサーバーのサーバー認証証明書既にに割り当てられた Skype ビジネス サーバー 2015 に、Skype からビジネス サーバー管理シェルの次のコマンドを実行します。
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

証明書の情報が返されない場合、サーバーからサーバーへの認証を使用する前に、トークンの発行者の証明書を割り当てる必要があります。 一般に、ビジネス サーバー 2015 の証明書のすべての Skype を OAuthTokenIssuer 証明書として使用できます。たとえば、ビジネス サーバー 2015 の既定の証明書は、Skype は OAuthTokenIssuer の証明書としても使用できます。 (OAUthTokenIssuer 証明書もできます、Web サーバー証明書を [件名] フィールドに、SIP ドメインの名前が含まれています)。これらは、サーバーからサーバーへの認証に使用する証明書の主な 2 つの要件: 1)、フロント エンド サーバーのすべての OAuthTokenIssuer の証明書と同じ証明書を構成する必要があります2) 証明書は 2048 ビット以上である必要があります。
  
サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。 要求し、新しい証明書を取得した後、フロント エンド サーバーのいずれかにログオンし、このいずれかのような Windows PowerShell コマンドを使用してインポートし、その証明書を割り当てます。
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

上記のコマンドのパスのパラメーターは、証明書ファイルに完全なパスを表し、パスワード パラメーターは、証明書に割り当てられたパスワードを表します。 1 回だけこの手順を実行する必要があります。 ビジネス サーバー レプリケーション サービスの Skype を復号化され、すべてのフロント エンド サーバーに証明書を展開するスケジュールされたタスクのセットを自動的に作成されますし。
  
または、既存の証明書をサーバーからサーバーへの認証証明書として使用できます。 (前述のように、既定の証明書として使用できます、サーバーからサーバーへの認証の証明書です。)Windows PowerShell コマンドの次の 2 つは、既定の証明書の拇印プロパティの値を取得し、サーバーからサーバーへの認証証明書を証明書の既定値にその値を使用します。
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

グローバル サーバーのサーバー認証証明書として機能するため、上記のコマンドで取得した証明書が構成されています。つまり、証明書には、複製し、する、すべてのフロント エンド サーバーによって使用されます。 もう一度、1 回と、フロント エンド サーバーの上の 1 つのみこのコマンドの実行のみです。 すべてのフロント エンド サーバーは、同じ証明書を使用する必要がありますは、各フロント エンド サーバーでない OAuthTokenIssuer 証明書を構成してください。 代わりに、1 回、証明書を構成し、ビジネス サーバー 2015 レプリケーション サーバーの Skype をその証明書を各サーバーにコピーする処理をできるようにします。
  
セット CsCertificate コマンドレットでは、問題の証明書を受け取るし、すぐに OAuthTokenIssuer の現在の証明書として機能するように、その証明書を構成します。 (Skype ビジネス サーバー 2015 の証明書の種類の 2 つのコピーを保持する: 現在の証明書や以前の証明書です)。OAuthTokenIssuer の証明書として機能するようにすぐに新しい証明書が必要な場合は、セット CsCertificate コマンドレットを使用する必要があります。
  
Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。たとえば、次のコマンドを実行すると、既定の証明書を取得し、2015 年 7 月 1 日から、その証明書が現在の OAuthTokenIssuer 証明書になるように構成します。
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

2015 年 7 月 1 日になると、新しい証明書が現在の OAuthTokenIssuer 証明書として構成され、"古い" OAuthTokenIssuer 証明書は以前の証明書として構成されます。
  
Windows PowerShell を使用したくない場合も 1 つのフロント エンド サーバーから証明書をエクスポートしてすべての他のフロント エンド サーバーに同じ証明書をインポートする証明書] MMC コンソールを使用することができます。 これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。
  
> [!CAUTION]
> この例では、各フロント エンド サーバー上の手順を実行しなければなりません。 エクスポートおよびインポートすると、このようにビジネス サーバー 2015 の Skype での証明書は各フロント エンド サーバーに証明書をレプリケートしません。 
  
すべてのフロント エンド サーバーに証明書をインポートした後、その証明書は Windows PowerShell ではなくビジネス サーバーの展開ウィザードは、Skype を使用して割り当てられます。 展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順に従います。
  
1. [開始] をクリックしてすべてのプログラムをクリックして、**ビジネス サーバー 2015 の Skype**、 **Skype ビジネス サーバーの展開ウィザード**] をクリックします。
    
2. 展開ウィザードで、**サーバーのビジネス システムの更新プログラムの Skype をインストールまたは**をクリックします。
    
3. ビジネス サーバー 2015 のページの Skype、見出しの下で**実行**] をクリックして**手順 3: インストールまたは割り当ての証明書を要求と、**。 (注: このコンピューターに証明書を既にインストールしているかどうかは、[**実行**] ボタンのラベル**の再実行**します)。
    
4. 証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。
    
5. 証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。
    
6. [**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。
    
7. [証明書の割り当ての概要] ページで、[**次へ**] をクリックします。
    
8. [コマンドを実行しています] ページで、[**完了**] をクリックします。
    
9. 証明書ウィザードと展開ウィザードを閉じます。
    

