---
title: ビジネス用の Skype で SEFAUtil ツールを展開します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: ビジネス サーバーの Skype で SEFAUtil ツールを展開します。
ms.openlocfilehash: 1b2f981a438b71b44eb5d4c760e98d1d777f7235
ms.sourcegitcommit: f9410a182f571d2a8ebe71ecd91ec97f83d8e077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2018
ms.locfileid: "25942808"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>ビジネス用の Skype で SEFAUtil ツールを展開します。
 
ビジネス サーバーの Skype で SEFAUtil ツールを展開します。
  
展開し、コール ピックアップのグループを管理、ビジネス サーバーのバージョンの SEFAUtil ツールは、Skype を使用する必要があります。 
  
> [!IMPORTANT]
> マイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 5 のランタイムは、SEFAUtil ツールを実行しようとするすべてのコンピューターにインストールしなければなりません。 ここからダウンロード:[ユニファイド コミュニケーション マネージ API 5.0 ランタイム](https://www.microsoft.com/en-us/download/details.aspx?id=47344)です。 ここでは、ランタイムが含まれています、UCMA 5 SDK をダウンロードすることもできます: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345)です。
  
すべてのフロント エンド プールで SEFAUtil ツールを実行するには、展開に。 SEFAUtil ツールを実行するには、必要がありますを実行するステップ 1、2、3、Skype からビジネス展開ウィザードのアプリケーションの信頼されたコンピューターにします。 SEFAUtil は、証明書と同様に、ローカル構成ストアが存在する必要があります。
  
> [!NOTE]
> SEFAUtil を実行しているの詳細については、ブログの記事を参照してください"[を実行している SEFAutil を取得する方法ですか?](https://go.microsoft.com/fwlink/?LinkId=278940)"です。 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1. RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. SEFAUtil ツールは、信頼済みアプリケーション プールに含まれるコンピューターでのみ実行できます。 必要な場合は、SEFAUtil を実行しようとするフロント エンド プール用の信頼されたアプリケーション プールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > プールの FQDN: SEFAUtil アプリケーション (通常は、ビジネスのフロント エンド サーバーまたはプールの Skype) をホストするプールまたはサーバーの FQDN です。
    > プール FQDN をレジストラー: ビジネスのフロント エンド サーバーまたはこのアプリケーション プールに関連付けられているプールの Skype の FQDN です。
    > プール サイト: このプールは、ホーム サーバーをサイトのサイト ID です。

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

6. まだインストールしていない場合は、[この場所](https://www.microsoft.com/en-us/download/details.aspx?id=52631)、およびインストールの手順 3 で作成する信頼されたアプリケーション プールにから SEFAUtil ツールのビジネスのサーバーのバージョンの Skype をダウンロードします。
    
7. 次のように、SEFAUtil ツールが正常に実行していることを確認します。 
    
    a. 管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。
    
    b. ユーザーの着信転送設定を表示します。 コマンド ラインで、次のコマンドを実行します。
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

ユーザーの着信転送設定が表示されます。
    

