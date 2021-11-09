---
title: サーバー内のバック エンド サーバーまたは Standard Editionサーバーにパッチを適用または更新Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '概要: 更新プログラムまたは更新プログラムをバック エンド サーバーにインストールする方法についてSkype for Business Server。'
ms.openlocfilehash: 55d81e97712abe51544a854bf175348526e9f29c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858214"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>サーバー内のバック エンド サーバーまたは Standard Editionサーバーにパッチを適用または更新Skype for Business Server
 
**概要:** このページで、更新プログラムまたは更新プログラムをバック エンド サーバーにインストールするSkype for Business Server。
  
このトピックでは、更新プログラムをバック エンド サーバーまたは Enterprise EditionサーバーにインストールするStandard Edition説明します。
  
アップグレード中に少なくとも 30 分間、バック エンド サーバーがダウンしている場合、ユーザーは復元モードに入る可能性があります。 アップグレードが完了し、バック エンド サーバーがプール内のフロント エンド サーバーに再び接続されると、ユーザーは完全な機能に戻ります。 アップグレードにかかる時間が 30 分未満の場合、ユーザーは影響を受け取る必要があります。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>バック エンド サーバーまたはサーバーを更新Standard Editionするには

1. CsAdministrator の役割のメンバーとして、アップグレードするサーバーにログオンします。
    
2. 更新プログラムをダウンロードし、ローカル ハード ディスクに展開します。
    
3. [管理シェルSkype for Business Server起動する: [**スタート**]をクリックし、[すべてのプログラム] をクリックし、[Skype for Business] をクリックし、[管理シェル **Skype for Business Serverクリックします**。
    
4. サービスSkype for Business Server停止します。 コマンドラインで、次のように入力します。
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. World Wide Web サービスを停止します。コマンドラインで、次のように入力します。
    
    ```PowerShell
    net stop w3svc
   ```

6. 管理シェル ウィンドウSkype for Business Server閉じます。
    
7. 更新プログラムをインストールします。
    
8. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
9. グローバル Skype for Business Server (GAC) -d アセンブリをキャッチするには、もう一度サービスを停止します。 コマンドラインで、次のように入力します。
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. World Wide Web サービスを再起動します。コマンドラインで、次のように入力します。
    
    ```PowerShell
    net start w3svc
    ```

11. 次のいずれかを実行して、SQL Serverデータベースに加えた変更を適用します。
    
    - これがバック エンド Enterprise Editionサーバーであり、アーカイブ データベースや監視データベースなど、このサーバー上にデータベースが複数ある場合は、コマンド ラインで次のように入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - これがバック エンド サーバー Enterprise Edition、このサーバーにデータベースが複数ある場合は、コマンド ラインで次を入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - このサーバーがサーバー Standard Edition、コマンド ラインで次のコマンドを入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
