---
title: Skype for Business Server 2015 のバックエンド サーバーまたは Standard Edition サーバーのパッチまたは更新
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '概要: ビジネス サーバーの Skype のバック エンド サーバー上の更新プログラムまたは修正プログラムをインストールする方法を説明します。'
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のバックエンド サーバーまたは Standard Edition サーバーのパッチまたは更新
 
**の概要:**ビジネス サーバーの Skype のバック エンド サーバー上の更新プログラムまたは修正プログラムをインストールする方法について説明します。
  
このトピックでは、エンタープライズ エディション バック エンド サーバーまたは Standard Edition サーバーに更新プログラムをインストールする方法について説明します。
  
場合は、バック エンド サーバーを 30 分以上にアップグレードするときに、ユーザーが復元モードに進みます。 アップグレードが完了すると、バック エンド サーバーがプール内のフロント エンド サーバーと接続がもう一度、すべての機能にユーザーが返されます。 アップグレードが 30 分未満の場合、ユーザーには影響ありません。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>バックエンド サーバーまたは Standard Edition サーバーを更新するには

1. アップグレードするサーバーに CsAdministrator の役割のメンバーとしてログオンします。
    
2. 更新をダウンロードして、ローカル ハードディスクに抽出します。
    
3. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス 2015年の Skype**をクリック**ビジネス サーバー管理シェルの Skype**.
    
4. Skype をビジネス サーバー サービスを停止します。 コマンド ラインで次を入力します。
    
    ```
    Stop-CsWindowsService
    ```

5. World Wide Web サービスを停止します。コマンド ラインで次を入力します。
    
    ```
    net stop w3svc
   ```

6. すべての Skype ビジネス サーバー管理シェル ウィンドウを閉じます。
    
7. 更新をインストールします。
    
8. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス 2015年の Skype**をクリック**ビジネス サーバー管理シェルの Skype**.
    
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


