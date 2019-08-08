---
title: Skype for Business で SEFAUtil ツールを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Skype for Business Server で SEFAUtil ツールを展開する。
ms.openlocfilehash: 1721f4d611a08a3054366e36b0ec9a3ebccf6c78
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245390"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Skype for Business で SEFAUtil ツールを展開する
 
Skype for Business Server で SEFAUtil ツールを展開する。
  
グループ通話のピックアップを展開して管理するには、Skype for Business Server バージョンの SEFAUtil ツールを使用する必要があります。 
  
> [!IMPORTANT]
> Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 5 ランタイムは、SEFAUtil ツールを実行する予定のコンピューターにインストールする必要があります。 ここからダウンロードしてください。[統合通信マネージ API 5.0 ランタイム](https://www.microsoft.com/en-us/download/details.aspx?id=47344)。 また、ランタイムを含む UCMA 5 SDK をダウンロードすることもできます。 [ucma 5.0 sdk](https://www.microsoft.com/en-us/download/details.aspx?id=47345)を参照してください。
  
SEFAUtil ツールは、展開の任意のフロントエンドプールで実行できます。 SEFAUtil ツールを実行するには、信頼済みアプリケーションコンピューターの Skype for Business 展開ウィザードで手順1、2、3を実行している必要があります。 SEFAUtil には、ローカル構成ストアと証明書の両方が含まれている必要があります。
  
> [!NOTE]
> SEFAUtil の実行の詳細については、ブログ記事「[SEFAUtil を実行する方法](https://go.microsoft.com/fwlink/?LinkId=278940)」を参照してください。 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1. Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. SEFAUtil ツールは、信頼済みアプリケーション プールに含まれるコンピューターでのみ実行できます。 必要に応じて、SEFAUtil を実行する予定のフロントエンドプールの信頼されたアプリケーションプールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > プールの FQDN: SEFAUtil アプリケーションをホストするサーバーまたはプールの FQDN (通常は、Skype for Business のフロントエンドサーバーまたはプール)。
    > プールレジストラー FQDN: このアプリケーションプールに関連付けられている Skype for Business フロントエンドサーバーまたはプールの FQDN。
    > プールサイト: このプールが所属しているサイトのサイト ID です。

4. SEFAUtil ツールを信頼済みアプリケーションとして定義します。コマンド ラインで、次のコマンドを実行します。
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 必要に応じて、別のポートを使用できます。 
  
5. 変更を加えたトポロジを有効にします。コマンド ラインで、次のコマンドを実行します。
    
   ```
   Enable-CsTopology
   ```

6. まだインストールしていない場合は、[この場所](https://www.microsoft.com/en-us/download/details.aspx?id=52631)から Skype For business Server バージョンの SEFAUtil ツールをダウンロードして、手順3で作成した信頼されたアプリケーションプールにインストールします。
    
7. 次のように、SEFAUtil ツールが正常に実行していることを確認します。 
    
    a. 管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。
    
    b. ユーザーの着信転送設定を表示します。 コマンド ラインで、次のコマンドを実行します。
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

ユーザーの着信転送設定が表示されます。
    

