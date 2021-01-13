---
title: Skype for Business で SEFAUtil ツールを展開する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Skype for Business Server での SEFAUtil ツールの展開。
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812387"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Skype for Business で SEFAUtil ツールを展開する
 
Skype for Business Server での SEFAUtil ツールの展開。
  
グループ通話ピックアップを展開および管理するには、Skype for Business Server バージョンの SEFAUtil ツールを使用する必要があります。 
  
> [!IMPORTANT]
> MICROSOFT Unified Communications Managed API (UCMA) 5 ランタイムは、SEFAUtil ツールを実行する予定のすべてのコンピューターにインストールする必要があります。 このサイトは [、Unified Communications Managed API 5.0 Runtime からダウンロードしてください](https://www.microsoft.com/download/details.aspx?id=47344)。 また、UCMA 5.0 SDK から、ランタイムを含む [UCMA 5 SDK をダウンロードすることもできます](https://www.microsoft.com/download/details.aspx?id=47345)。
  
SEFAUtil ツールは、展開内の任意のフロントエンド プールで実行できます。 SEFAUtil ツールを実行するには、信頼されたアプリケーション コンピューターで Skype for Business 展開ウィザードから手順 1、2、および 3 を実行する必要があります。 SEFAUtil では、ローカル構成ストアと証明書が必要です。
  
> [!NOTE]
> SEFAUtil の実行の詳細については、ブログ記事[「SEFAutil](https://go.microsoft.com/fwlink/?LinkId=278940)を実行する方法」を参照してください。 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
3. SEFAUtil ツールは、信頼されたアプリケーション プールの一部であるコンピューターでのみ実行できます。 必要に応じて、SEFAUtil を実行する予定のフロントエンド プールの信頼されたアプリケーション プールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > プールの FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常は Skype for Business フロントエンド サーバーまたはプール)。
    > プール レジストラー FQDN: このアプリケーション プールに関連付けられている Skype for Business フロントエンド サーバーまたはプールの FQDN。
    > プール サイト: このプールがホームであるサイトのサイト ID。

4. SEFAUtil ツールを信頼されたアプリケーションとして定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 必要に応じて、別のポートを使用できます。 
  
5. 変更を加えたトポロジを有効にする。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   Enable-CsTopology
   ```

6. まだダウンロードしていない場合は、この場所から Skype for Business Server バージョンの[](https://www.microsoft.com/download/details.aspx?id=52631)SEFAUtil ツールをダウンロードし、手順 3 で作成した信頼されたアプリケーション プールにインストールします。
    
7. 次のように、SEFAUtil ツールが正しく実行されていることを確認します。 
    
    a.  管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの呼び出し転送設定を表示します。
    
    b. ユーザーの呼び出し転送設定を表示します。 コマンド ラインで、次のコマンドを実行します。
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

ユーザーの呼び出し転送設定が表示されます。
    

