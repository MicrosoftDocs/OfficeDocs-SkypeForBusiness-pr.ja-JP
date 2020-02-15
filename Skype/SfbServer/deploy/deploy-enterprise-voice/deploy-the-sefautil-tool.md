---
title: Skype for Business で SEFAUtil ツールを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server に SEFAUtil ツールを展開します。
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986812"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Skype for Business で SEFAUtil ツールを展開する
 
Skype for Business Server に SEFAUtil ツールを展開します。
  
グループ通話ピックアップを展開および管理するには、Skype for Business Server バージョンの SEFAUtil ツールを使用する必要があります。 
  
> [!IMPORTANT]
> Microsoft 統合コミュニケーション管理 API (UCMA) 5 ランタイムは、SEFAUtil ツールを実行する予定の任意のコンピューターにインストールする必要があります。 この記事は、「[統合コミュニケーションマネージ API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344)」にダウンロードしてください。 また、次のように、ランタイムを含む UCMA 5 SDK をダウンロードすることもできます。 [ucma 5.0 sdk](https://www.microsoft.com/download/details.aspx?id=47345)。
  
SEFAUtil ツールは、展開内の任意のフロントエンドプールで実行できます。 SEFAUtil ツールを実行するには、信頼されたアプリケーションコンピューターで Skype for Business 展開ウィザードから手順1、2、および3を実行する必要があります。 SEFAUtil には、ローカル構成ストアと証明書の両方が存在する必要があります。
  
> [!NOTE]
> SEFAUtil の実行の詳細については、ブログ記事「[How to Get SEFAUtil running?](https://go.microsoft.com/fwlink/?LinkId=278940)」を参照してください。 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「**セットアップのアクセス許可の委任**」に説明されている必要なユーザー権限を使用してログオンします。
    
2. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。
    
3. SEFAUtil ツールは、信頼されたアプリケーションプールの一部であるコンピューターでのみ実行できます。 必要に応じて、SEFAUtil の実行を計画しているフロントエンドプールの信頼されたアプリケーションプールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > [プールの FQDN]: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常は、Skype for Business のフロントエンドサーバーまたはプール)。
    > プールレジストラー FQDN: このアプリケーションプールに関連付けられている Skype for Business フロントエンドサーバーまたはプールの FQDN。
    > プールサイト: このプールが所属しているサイトのサイト ID。

4. SEFAUtil ツールを信頼済みアプリケーションとして定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 必要に応じて、別のポートを使用することができます。 
  
5. 変更したトポロジを有効にします。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   Enable-CsTopology
   ```

6. まだお持ちでない場合は、[この場所](https://www.microsoft.com/download/details.aspx?id=52631)から Skype For business Server バージョンの SEFAUtil ツールをダウンロードして、手順3で作成した信頼されたアプリケーションプールにインストールしてください。
    
7. SEFAUtil ツールが正常に実行されていることを、次のように確認します。 
    
    a.  管理者特権を使用して Windows コマンドプロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。
    
    b.  ユーザーの着信転送設定を表示します。 コマンド ラインで、次のコマンドを実行します。
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

ユーザーの着信転送設定が表示されます。
    

