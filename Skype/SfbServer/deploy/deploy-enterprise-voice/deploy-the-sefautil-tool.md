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
ms.openlocfilehash: 013890e3b65dfd3a8360da859a1c9179fa9b5a13
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105803"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Skype for Business で SEFAUtil ツールを展開する
 
Skype for Business Server での SEFAUtil ツールの展開。
  
グループ通話ピックアップを展開および管理するには、Skype for Business Server バージョンの SEFAUtil ツールを使用する必要があります。 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 ランタイムは、SEFAUtil ツールを実行する予定の任意のコンピューターにインストールする必要があります。 ここにダウンロードする: [ユニファイド コミュニケーションマネージ API 5.0 ランタイム](https://www.microsoft.com/download/details.aspx?id=47344)。 また、UCMA 5 SDK (ランタイムを含む) をダウンロードすることもできます [。UCMA 5.0 SDK を次に示します](https://www.microsoft.com/download/details.aspx?id=47345)。
  
展開内の任意のフロントエンド プールで SEFAUtil ツールを実行できます。 SEFAUtil ツールを実行するには、信頼できるアプリケーション コンピューターで Skype for Business 展開ウィザードから手順 1、2、および 3 を実行する必要があります。 SEFAUtil では、証明書と同様に、ローカル構成ストアが存在する必要があります。
  
> [!NOTE]
> SEFAUtil の実行の詳細については、ブログ記事[「SEFAutil を実行する方法」を参照してください。](/archive/blogs/jenstr/how-to-get-sefautil-running) 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1. 「代理セットアップのアクセス許可」の説明に従って、Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でインストールされているコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. SEFAUtil ツールは、信頼できるアプリケーション プールの一部であるコンピューターでのみ実行できます。 必要に応じて、SEFAUtil を実行する予定のフロント エンド プールの信頼できるアプリケーション プールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > プール FQDN: SEFAUtil アプリケーション (通常は Skype for Business フロントエンド サーバーまたはプール) をホストするサーバーまたはプールの FQDN。
    > プール レジストラー FQDN: このアプリケーション プールに関連付けられている Skype for Business フロントエンド サーバーまたはプールの FQDN。
    > プール サイト: このプールがホームであるサイトのサイト ID。

4. SEFAUtil ツールを信頼できるアプリケーションとして定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 必要に応じて、別のポートを使用できます。 
  
5. 変更を使用してトポロジを有効にする。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   Enable-CsTopology
   ```

6. まだインストールしていない場合は、この場所から Skype for Business Server バージョンの[](https://www.microsoft.com/download/details.aspx?id=52631)SEFAUtil ツールをダウンロードし、手順 3 で作成した信頼できるアプリケーション プールにインストールします。
    
7. 次のように、SEFAUtil ツールが正しく実行されていることを確認します。 
    
    a. Windows コマンド プロンプトから管理者特権でツールを実行し、展開でユーザーの通話転送設定を表示します。
    
    b. ユーザーの通話転送設定を表示します。 コマンド ラインで、次のコマンドを実行します。
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

ユーザーの通話転送設定が表示されます。
