---
title: SCOM 監視の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Microsoft Skype for Business Server 2019 に移行した後は、いくつかのタスクを実行して、System Center Operations Manager で動作するように Skype for Business Server 2019 を設定する必要があります。
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284502"
---
# <a name="configure-scom-monitoring"></a>SCOM 監視の構成

Skype for Business Server 2019 に移行した後は、いくつかのタスクを実行して、System Center Operations Manager で動作するように Skype for Business Server 2019 を設定する必要があります。
  
- セントラル検出ロジックを管理するように選択されたサーバーに更新プログラムを適用します。
    
- セントラル探索候補サーバーのレジストリキーを更新します。
    
- "候補" セントラル探索ノードを上書きするように、プライマリ System Center Operations Manager management サーバーを構成します。
    
これらの各タスクを実行する手順については、以下で説明します。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>セントラル検出ロジックを管理するように選択されたサーバーに更新プログラムを適用します。

1. System Center Operations Manager エージェントファイルがインストールされ、候補探索ノードとして構成されているサーバーを選びます。 
    
2. このサーバーに更新プログラムを適用します。 「[更新プログラムを適用](apply-updates.md)する」を参照してください。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>セントラル探索候補サーバーのレジストリキーを更新します。

1. サーバー上でセントラル検出ロジックを管理することを選択した場合は、Windows PowerShell コマンドウィンドウを開きます。 
    
2. コマンドラインで、次のように入力します。
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > レジストリを編集すると、レジストリキーが既に存在する場合に、コマンドが失敗するというエラーが発生する場合があります。 この問題が発生した場合は、エラーを無視しても問題ありません。 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>主要な System Center Operations Manager management server を構成して、[セントラル探索の候補となるサービスの管理者ノードを上書きする。

1. System Center Operations Manager コンソールがインストールされているコンピューターで、[**管理パックのオブジェクト**] を展開し、[**オブジェクト**検出] を選択します。
    
2. [**範囲の変更**] をクリックする
    
3. [**スコープ管理パックのオブジェクト**] ページで、[ **LS 検出候補**] を選択します。
    
4. **LS 検出候補の有効値**を、前の手順で選択した候補サーバーの名前に上書きします。 
    
変更を完了するには、System Center Operations Manager ルート管理サーバーで正常性サービスを再起動します。
  

