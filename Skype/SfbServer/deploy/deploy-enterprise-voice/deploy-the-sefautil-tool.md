---
title: SEFAUtil ツールをサーバーに展開Skype for Business
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
description: SEFAUtil ツールをサーバーに展開Skype for Business Server。
ms.openlocfilehash: 5683dab35a51a088b89f410c11bd0713a8256496f85d11c7190d44f82528a3c9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331869"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>SEFAUtil ツールをサーバーに展開Skype for Business
 
SEFAUtil ツールをサーバーに展開Skype for Business Server。
  
グループ通話ピックアップを展開および管理するには、SEFAUtil ツールの Skype for Business Serverバージョンを使用する必要があります。 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 ランタイムは、SEFAUtil ツールを実行する予定の任意のコンピューターにインストールする必要があります。 ここにダウンロードする: [ユニファイド コミュニケーションマネージ API 5.0 ランタイム](https://www.microsoft.com/download/details.aspx?id=47344)。 また、UCMA 5 SDK (ランタイムを含む) をダウンロードすることもできます [。UCMA 5.0 SDK を次に示します](https://www.microsoft.com/download/details.aspx?id=47345)。
  
展開内の任意のフロントエンド プールで SEFAUtil ツールを実行できます。 SEFAUtil ツールを実行するには、信頼済みアプリケーション コンピューターの Skype for Business 展開ウィザードから手順 1、2、および 3 を実行する必要があります。 SEFAUtil では、証明書と同様に、ローカル構成ストアが存在する必要があります。
  
> [!NOTE]
> SEFAUtil の実行の詳細については、ブログ記事[「SEFAutil を実行する方法」を参照してください。](/archive/blogs/jenstr/how-to-get-sefautil-running) 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または「代理セットアップのアクセス許可」の説明に従って必要なユーザー権限でログオン **します。**
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. SEFAUtil ツールは、信頼できるアプリケーション プールの一部であるコンピューターでのみ実行できます。 必要に応じて、SEFAUtil を実行する予定のフロント エンド プールの信頼できるアプリケーション プールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > プール FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常、Skype for Businessフロントエンド サーバーまたはプール)。
    > プール レジストラー FQDN: このアプリケーション プールにSkype for Businessフロントエンド サーバーまたはプールの FQDN。
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

6. まだインストールしていない場合は、この場所から Skype for Business Server バージョンの SEFAUtil ツールを[](https://www.microsoft.com/download/details.aspx?id=52631)ダウンロードし、手順 3 で作成した信頼できるアプリケーション プールにインストールします。
    
7. 次のように、SEFAUtil ツールが正しく実行されていることを確認します。 
    
    a. 管理者特権を持つ Windows コマンド プロンプトからツールを実行して、展開内のユーザーの通話転送設定を表示します。
    
    b. ユーザーの通話転送設定を表示します。 コマンド ラインで、次のコマンドを実行します。
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

ユーザーの通話転送設定が表示されます。
