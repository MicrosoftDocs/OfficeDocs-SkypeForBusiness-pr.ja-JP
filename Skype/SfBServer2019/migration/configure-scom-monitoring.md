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
description: Microsoft Skype for Business Server 2019 に移行した後、Skype for Business Server 2019 を構成して System Center Operations Manager を構成する必要があります。
ms.openlocfilehash: 477fbd3c405328ffac4aa70a722120d375e95b295bf5a23d19882248d1ece54e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279615"
---
# <a name="configure-scom-monitoring"></a>SCOM 監視の構成

2019 Skype for Business Serverに移行した後、Skype for Business Server 2019 を構成して、System Center Operations Manager を構成する必要があります。
  
- 中央検出ロジックを管理するために選択されたサーバーに更新プログラムを適用します。
    
- 中央検出候補サーバーのレジストリ キーを更新する。
    
- 候補の中央探索ノードSystem Center上書きするプライマリ サーバーを Operations Manager 管理サーバーに構成します。
    
各タスクを実行する手順を次に示します。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>中央検出ロジックを管理するために選択されたサーバーに更新プログラムを適用します。

1. System Center Operations Manager エージェント ファイルがインストールされ、候補検出ノードとして構成されているサーバーを選択します。 
    
2. このサーバーに更新プログラムを適用します。 「更新プログラムの適用 [」を参照してください](apply-updates.md)。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>中央検出候補サーバーのレジストリ キーを更新する。

1. 中央検出ロジックを管理するために選択されたサーバーで、新しいWindows PowerShell開きます。 
    
2. コマンド ラインで、次のように入力します。
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > レジストリを編集すると、"レジストリ キーが既に存在する場合はコマンドが失敗する" というエラーが発生することがあります。このエラーは無視しても問題ありません。 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>候補の中央探索監視System Center上書きするために、Operations Manager 管理サーバーのプライマリ サーバーを構成します。

1. System Center Operations Manager コントロールがインストールされているコンピューターで、[**管理パック オブジェクト**] を展開し、[**オブジェクト検出**] を選択します。
    
2. [スコープ **の変更] をクリックします。**
    
3. [**管理パック オブジェクトのスコープ設定**] ページで、[**LS Discovery Candidate**] を選択します。
    
4. 前の手順で選択した候補サーバーの名前の [**LS Discovery Candidate Effective Value**] を上書きします。 
    
変更を完了するには、Operations Manager ルート管理サーバーのSystem Center正常性サービスを再起動します。
  

