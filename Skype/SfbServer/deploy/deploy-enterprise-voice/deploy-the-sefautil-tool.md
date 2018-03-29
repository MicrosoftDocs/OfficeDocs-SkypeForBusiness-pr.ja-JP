---
title: Skype for Business 2015 での SEFAUtil ツールの展開
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: ビジネス サーバーの Skype で SEFAUtil ツールを展開します。
ms.openlocfilehash: eba4c6d9c6d0c48256621537350a822c3314ca40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>Skype for Business 2015 での SEFAUtil ツールの展開
 
ビジネス サーバーの Skype で SEFAUtil ツールを展開します。
  
展開し、コール ピックアップのグループを管理、ビジネス サーバーのバージョンの SEFAUtil ツールは、Skype を使用する必要があります。 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK を、SEFAUtil ツールを実行する予定のすべてのコンピューターにインストールする必要があります。 
  
すべてのフロント エンド プールで SEFAUtil ツールを実行するには、展開に。
  
> [!NOTE]
> SEFAUtil を実行しているの詳細については、Technet のブログ記事を参照してください"[を実行している SEFAutil を取得する方法ですか?](https://go.microsoft.com/fwlink/?LinkId=278940)"です。 
  
### <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1. RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. SEFAUtil ツールは、信頼済みアプリケーション プールに含まれるコンピューターでのみ実行できます。 必要な場合は、SEFAUtil を実行しようとするフロント エンド プール用の信頼されたアプリケーション プールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

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
    

