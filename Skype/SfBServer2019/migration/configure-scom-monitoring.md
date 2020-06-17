---
title: SCOM 監視の構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft Skype for Business Server 2019 に移行した後、いくつかのタスクを実行して、System Center Operations Manager と連携するように Skype for Business Server 2019 を構成する必要があります。
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754047"
---
# <a name="configure-scom-monitoring"></a>SCOM 監視の構成

Skype for business Server 2019 に移行した後、いくつかのタスクを実行して、System Center Operations Manager と連携するように Skype for Business Server 2019 を構成する必要があります。
  
- 中央検出ロジックを管理するために選択したサーバーに更新プログラムを適用します。
    
- 中央検出候補サーバーのレジストリ キーを更新する。
    
- プライマリの System Center Operations Manager 管理サーバーを構成して、[中央探索の候補」ノードを上書きします。
    
各タスクを実行する手順を次に示します。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>中央検出ロジックを管理するために選択したサーバーに更新プログラムを適用します。

1. System Center Operations Manager エージェント ファイルがインストールされ、候補検出ノードとして構成されているサーバーを選択します。 
    
2. このサーバーに更新プログラムを適用します。 「 [Apply updates](apply-updates.md)」を参照してください。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>中央検出候補サーバーのレジストリ キーを更新する。

1. 中央検出ロジックを管理することを選択したサーバーで、Windows PowerShell コマンドウィンドウを開きます。 
    
2. コマンド ラインで、次のように入力します。
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>プライマリの System Center Operations Manager 管理サーバーを構成して、[中央探索の候補監視ノードの候補を上書きします。

1. System Center Operations Manager コントロールがインストールされているコンピューターで、[**管理パック オブジェクト**] を展開し、[**オブジェクト検出**] を選択します。
    
2. [**スコープの変更**] をクリックします。
    
3. [**管理パック オブジェクトのスコープ設定**] ページで、[**LS Discovery Candidate**] を選択します。
    
4. 前の手順で選択した候補サーバーの名前の [**LS Discovery Candidate Effective Value**] を上書きします。 
    
変更を確定するには、System Center Operations Manager のルート管理サーバーで正常性サービスを再起動します。
  

