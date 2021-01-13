---
title: Skype for Business Server でバック エンド サーバーまたは Standard Edition サーバーにパッチを適用または更新する
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '概要: Skype for Business Server のバック エンド サーバーに更新プログラムまたは更新プログラムをインストールする方法について学習します。'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826307"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Skype for Business Server のバック エンド サーバーまたは Standard Edition サーバーにパッチを適用または更新する
 
**概要:** Skype for Business Server のバック エンド サーバーに更新プログラムまたは更新プログラムをインストールする方法について学習します。
  
このトピックでは、Enterprise Edition のバック エンド サーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。
  
アップグレード中に少なくとも 30 分間、バック エンド サーバーがダウンした場合、ユーザーは復元モードになります。 アップグレードが完了し、バック エンド サーバーがプール内のフロントエンド サーバーに再度接続されると、ユーザーは完全な機能に戻ります。 アップグレードにかかる時間が 30 分未満の場合、ユーザーに影響は与えされません。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>バック エンド サーバーまたは Standard Edition サーバーを更新するには

1. CsAdministrator の役割のメンバーとして、アップグレードするサーバーにログオンします。
    
2. 更新プログラムをダウンロードし、ローカル ハード ディスクに展開します。
    
3. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
4. Skype for Business Server サービスを停止します。 コマンドラインで、次のように入力します。
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. World Wide Web サービスを停止します。 コマンドラインで、次のように入力します。
    
    ```PowerShell
    net stop w3svc
   ```

6. すべての Skype for Business Server 管理シェル ウィンドウを閉じます。
    
7. 更新プログラムをインストールします。
    
8. Skype for Business Server 管理シェルを起動します **。[スタート**] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
9. Skype for Business Server サービスを再度停止して、グローバル アセンブリ キャッシュ (GAC) -d アセンブリをキャッチします。 コマンドラインで、次のように入力します。
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. World Wide Web サービスを再起動します。 コマンドラインで、次のように入力します。
    
    ```PowerShell
    net start w3svc
    ```

11. 次のいずれかの方法で、SQL Serverデータベースに加えた変更を適用します。
    
    - Enterprise Edition のバック エンド サーバーで、アーカイブ データベースや監視データベースなど、このサーバーにデータベースが一覧に表示されなき場合は、コマンド ラインで次のように入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Enterprise Edition のバック エンド サーバーで、このサーバーにデータベースが一覧に表示されている場合は、コマンド ラインで次を入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - これが Standard Edition サーバーの場合は、コマンド ラインで次を入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
