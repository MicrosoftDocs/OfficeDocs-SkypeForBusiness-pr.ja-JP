---
title: Skype for Business Server のバックエンドサーバーまたは Standard Edition サーバーを修正または更新する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '概要: Skype for Business Server のバックエンドサーバーに更新プログラムまたは更新プログラムをインストールする方法について説明します。'
ms.openlocfilehash: a88224c508426d16217adb87693515314b03e40f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991502"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Skype for Business Server のバックエンドサーバーまたは Standard Edition サーバーを修正または更新する
 
**概要:** Skype for Business Server のバックエンドサーバーに更新プログラムまたは更新プログラムをインストールする方法について説明します。
  
このトピックでは、Enterprise Edition バックエンドサーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。
  
アップグレード中に少なくとも30分間バックエンドサーバーが停止している場合、ユーザーは回復性モードに移行することがあります。 アップグレードが完了し、バックエンドサーバーがプール内のフロントエンドサーバーに再度接続されると、ユーザーは完全な機能に戻ります。 アップグレードが 30 分未満の場合、ユーザーには影響ありません。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>バックエンド サーバーまたは Standard Edition サーバーを更新するには

1. アップグレードするサーバーに CsAdministrator の役割のメンバーとしてログオンします。
    
2. 更新をダウンロードして、ローカル ハードディスクに抽出します。
    
3. Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype For business**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
4. Skype for Business Server サービスを停止します。 コマンド ラインで次を入力します。
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. World Wide Web サービスを停止します。 コマンド ラインで次を入力します。
    
    ```PowerShell
    net stop w3svc
   ```

6. すべての Skype for Business Server 管理シェルウィンドウを閉じます。
    
7. 更新をインストールします。
    
8. Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype For business**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
9. Skype for Business Server サービスをもう一度停止して、グローバルアセンブリキャッシュ (GAC) アセンブリをキャッチします。 コマンド ラインで次を入力します。
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. World Wide Web サービスを再起動します。コマンド ラインで次を入力します。
    
    ```PowerShell
    net start w3svc
    ```

11. 次のいずれかを実行して、SQL Server データベースに対する変更を適用します。
    
    - Enterprise Edition バックエンドサーバーで、データベースのアーカイブや監視など、このサーバー上に併置されたデータベースがない場合は、コマンドラインで次のように入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Enterprise Edition バックエンドサーバーで、このサーバーに併置されたデータベースがある場合は、コマンドラインで次のように入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Standard Edition サーバーの場合は、コマンドラインで次のように入力します。
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
