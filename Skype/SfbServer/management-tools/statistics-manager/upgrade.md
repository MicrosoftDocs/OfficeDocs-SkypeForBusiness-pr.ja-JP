---
title: Skype for Business Server の統計情報マネージャーのアップグレード
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: '概要: このトピックを参照して、統計マネージャーをアップグレードする方法についてSkype for Business Server。'
ms.openlocfilehash: caa2a5f7576a046c990315b638e618a379dd039e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611986"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server の統計情報マネージャーのアップグレード
 
**概要:** このトピックを参照して、統計マネージャーをアップグレードする方法についてSkype for Business Server。
  
このトピックでは、Skype for Business Server の統計マネージャーの既存のインストールをアップグレードする方法について説明します。Skype for Business Server の正常性とパフォーマンスのデータをリアルタイムで表示できる強力なツールです。 数百のサーバーでパフォーマンス データを数秒ごとにポーリングし、統計マネージャー Web サイトで即座に結果を表示できます。 
  
統計マネージャーとリリース 2.0 の新機能の詳細については、「Plan [for Statistics Manager for Skype for Business Server」](plan.md)および「Deploy Statistics Manager for Skype for Business Server」を[参照してください](deploy.md)。
  
アップグレードには、次の 2 つの方法があります。
  
- **自動アップグレード。** このメソッドは、自動化されたスクリプトを使用します。 これは最も簡単な方法であり、すべてのアップグレード シナリオに適用できる必要があります。
    
- **手動アップグレード。** この方法は、自動アップグレードが失敗する異常な場合のバックアップ 計画として提供されます。
    
## <a name="prerequisites"></a>前提条件

アップグレードする前に、次の情報を確認してください。
  
- アクティブ リスナー証明書の拇印
    
- リスナー サービス パスワード (リスナーとすべてのエージェントのインストール時に入力)
    
- Web サイトの SSL 証明書の構成
    
## <a name="automated-upgrade"></a>自動アップグレード

スクリプトは、現在の証明書情報とリスナー パスワードを収集し、古いバージョンの製品をアンインストールしてから、新しいバージョンの製品をインストールします。 サーバーにインストールされている Redis インスタンスには触れないので、キャッシュに格納されているデータはアップグレード プロセスを通じて保持されます。
  
1. 新しいバージョンのエージェント、リスナー、Web サイトの MSI ファイルと、Update-StatsMan.ps1 スクリプトをリスナー コンピューター上の 1 つのフォルダーに配置します。
    
2. 管理用 PowerShell ウィンドウを開きます。 リスナー コンポーネントをアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Statistics Manager サービスのパスワードは、インストーラーに渡されるコマンド ラインにクリア テキストで表示されます。 必要に応じてモニターをシールドしてください。 
  
1. スクリプトを実行すると、古いバージョンの製品をアンインストールするように求めるメッセージが表示されます。 回答 はい。
    
2. リスナー サービスが実行されている場合は、続行する前にアプリケーションを閉じるメッセージが表示されます。 アプリケーションの終了を許可します (Statistics Manager リスナー サービスは停止されます)。
    
3. インストール プロセスを続行します。 サービス パスワードと証明書の拇印が事前に入力されている必要があります。 保存されていない場合は、続行する前に保存した値を追加します。
    
4. 管理用 PowerShell ウィンドウを開きます。 Web サイト コンポーネントをアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. スクリプトを実行すると、古いバージョンの製品をアンインストールするように求めるメッセージが表示されます。 回答 はい。
    
6. エージェント サービスが実行されている場合は、続行する前にアプリケーションを閉じるメッセージが表示されます。 アプリケーションの終了を許可します (StatsMan エージェント サービスは停止されます)。
    
7. インストール プロセスを続行します。 サービス パスワードと証明書の拇印が事前に入力されている必要があります。 保存されていない場合は、続行する前に保存した値を追加します。
    
8. 管理用 PowerShell ウィンドウを開きます。 Agent コンポーネントをアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. スクリプトを実行すると、古いバージョンの製品をアンインストールするように求めるメッセージが表示されます。 回答 はい。
    
10. インストール プロセスを続行します。 Web サイト ポートが事前に設定されているのに注意してください。 設定されていない場合は、続行する前に保存した値を追加します。
    
11. ブラウザーを使用して Web サイトが正常に動作しているのを確認します。
    
> [!NOTE]
> エージェントのアップグレードは、-NoPrompt スイッチと一緒に使用できます。 これにより、アンインストール/インストール プロセスがサイレント モードで実行され、PSExec などのツールが多数のサーバーでリモートでアップグレードを実行できます。 
  
### <a name="manual-upgrade"></a>手動アップグレード

何らかの理由で自動アップグレードが失敗した場合は、次のように手動アップグレードをいつでも実行できます。
  
1. リスナー コンピューターで、リスナー、Web サイト、およびエージェント (このサーバーにインストールされている場合) を、プログラムと機能します。 
    
    > [!NOTE]
    >  Redis をインストールし、キャッシュ内のデータがアップグレード プロセスを通じて維持されます。
  
2. 新しいバージョンのコンポーネントをインストールします。そのコンポーネントの入力を求めるメッセージが表示されたら、上記で保存した値も含まれます。 コンポーネントのインストールの詳細については、「Deploy [Statistics Manager」を参照してください。](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>関連情報
<a name="BKMK_Fixed"> </a>

詳細については、次のトピックを参照してください。
  
- [Skype for Business Server の Statistics Manager の計画](plan.md)
    
- [Skype for Business Server の Statistics Manager の展開](deploy.md)
    
- [Skype for Business Server の Statistics Manager のトラブルシューティング](troubleshoot.md)
