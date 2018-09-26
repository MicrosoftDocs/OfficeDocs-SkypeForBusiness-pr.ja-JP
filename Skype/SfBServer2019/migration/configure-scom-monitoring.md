---
title: SCOM で監視を構成します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: に移行した後 Microsoft Skype ビジネス サーバー 2019 の System Center Operations Manager を使用するサーバー 2019 のビジネス用の Skype を構成するのには、いくつかのタスクを完了する必要があります。
ms.openlocfilehash: c0d15d14e158c33cda5e623ea978a0bc4f0bb920
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028937"
---
# <a name="configure-scom-monitoring"></a>SCOM で監視を構成します。

に移行した後 Skype ビジネス サーバー 2019 の System Center Operations Manager を使用するサーバー 2019 のビジネス用の Skype を構成するのには、いくつかのタスクを完了する必要があります。
  
- 中央の検出ロジックを管理することを選択するサーバーに更新プログラムを適用します。
    
- 中央の検索候補のサーバーのレジストリ キーを更新します。
    
- 候補の中心的な探索ノードを上書きする、プライマリの System Center Operations Manager 管理サーバーを構成します。
    
これらのタスクを実行するための手順が記載されています。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>中央の検出ロジックを管理することを選択するサーバーに更新プログラムを適用します。

1. System Center Operations Manager エージェントのファイルがインストールされ、候補探索ノードとして構成されているサーバーを選択します。 
    
2. このサーバーに更新プログラムを適用します。 [更新プログラムの適用](apply-updates.md)のトピックを参照してください。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>中央の検索候補のサーバーのレジストリ キーを更新します。

1. 中央の検出ロジックを管理することを選択、サーバー上には、Windows PowerShell のコマンド ウィンドウを開きます。 
    
2. コマンドラインで、次のように入力します。
    
  ```
  New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
  ```

  ```
  New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
  ```

    > [!NOTE]
    > レジストリを編集するたびに、レジストリ キーが既に存在する場合、コマンドが失敗しましたというエラーが発生するように。 この状況が発生する場合は、エラーを無視してかまいません。 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>候補の中心的な検出の監視ノードを上書きする、プライマリの System Center Operations Manager 管理サーバーを構成します。

1. System Center Operations Manager コンソールがインストールされているコンピューター、[**管理パック オブジェクト**を展開し、**オブジェクト検出**します。
    
2. [**スコープの変更**] をクリックします。
    
3. **管理パック オブジェクトのスコープ**] ページで、 **LS の検索候補**を選択します。
    
4. **LS 検索候補の有効値**の前の手順で選択した候補のサーバーの名前をオーバーライドします。 
    
変更内容を確定するには、システム センター操作マネージャー ルートの管理サーバーの稼働状態サービスを再起動します。
  

