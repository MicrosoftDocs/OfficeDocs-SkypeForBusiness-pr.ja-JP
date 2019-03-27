---
title: 修正プログラムを適用またはビジネスのサーバーの Skype のバック エンド サーバーまたは Standard Edition サーバーを更新します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '概要: ビジネス サーバーの Skype のバック エンド サーバー上の更新プログラムまたは修正プログラムをインストールする方法を説明します。'
ms.openlocfilehash: 7919d437e5111d32f3f51fa19a1880714800666b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884154"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>修正プログラムを適用またはビジネスのサーバーの Skype のバック エンド サーバーまたは Standard Edition サーバーを更新します。
 
**の概要:** ビジネス サーバーの Skype のバック エンド サーバー上の更新プログラムまたは修正プログラムをインストールする方法について説明します。
  
このトピックでは、エンタープライズ エディション バック エンド サーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。
  
場合は、バック エンド サーバーを 30 分以上にアップグレードするときに、ユーザーが復元モードに進みます。 アップグレードが完了すると、バック エンド サーバーがプール内のフロント エンド サーバーと接続がもう一度、すべての機能にユーザーが返されます。 アップグレードが 30 分未満の場合、ユーザーには影響ありません。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>バックエンド サーバーまたは Standard Edition サーバーを更新するには

1. アップグレードするサーバーに CsAdministrator の役割のメンバーとしてログオンします。
    
2. 更新をダウンロードして、ローカル ハードディスクに抽出します。
    
3. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネスの Skype**をクリック**ビジネス サーバー管理シェルの Skype**.
    
4. Skype をビジネス サーバー サービスを停止します。 コマンド ラインで次を入力します。
    
    ```
    Stop-CsWindowsService
    ```

5. World Wide Web サービスを停止します。 コマンド ラインで次を入力します。
    
    ```
    net stop w3svc
   ```

6. すべての Skype ビジネス サーバー管理シェル ウィンドウを閉じます。
    
7. 更新をインストールします。
    
8. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネスの Skype**をクリック**ビジネス サーバー管理シェルの Skype**です。
    
9. -D のアセンブリをグローバル アセンブリ キャッシュ (GAC) をキャッチするには、もう一度ビジネス サーバー サービスの Skype を停止します。 コマンド ラインで次を入力します。
    
    ```
    Stop-CsWindowsService
    ```

10. World Wide Web サービスを再起動します。コマンド ラインで次を入力します。
    
    ```
    net start w3svc
    ```

11. 次のいずれかを実行して、SQL Server データベースに対する変更を適用します。
    
    - エンタープライズ エディション バック エンド サーバー、アーカイブなど、サーバー上に配置されているデータベースやデータベースの監視が存在しない、する場合は、コマンド ・ ラインで次を入力します。
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - これは、エンタープライズ エディション バック エンド サーバーであり、このサーバー上に配置されているデータベースがある場合、は、コマンド ・ ラインで次を入力します。
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Standard Edition サーバーの場合は、コマンド ・ ラインで次を入力します。
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
