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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: '概要: このトピックでは、Skype for Business Server の Statistics Manager をアップグレードする方法について説明します。'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821767"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server の統計情報マネージャーのアップグレード
 
**概要:** このトピックでは、Skype for Business Server の Statistics Manager をアップグレードする方法について説明します。
  
このトピックでは、Skype for Business Server の Statistics Manager の既存のインストールをアップグレードする方法について説明します。これは、Skype for Business Server の正常性とパフォーマンスのデータをリアルタイムで表示できる強力なツールです。 数秒ごとに数百のサーバーでパフォーマンス データをポーリングし、統計情報マネージャー Web サイトで即座に結果を表示できます。 
  
Statistics Manager とリリース 2.0 の新機能の詳細については [、「Plan for Statistics Manager for Skype for Business Server」](plan.md) および [「Deploy Statistics Manager for Skype for Business Server」](deploy.md)を参照してください。
  
アップグレードには 2 つの方法があります。
  
- **自動アップグレード。** このメソッドでは、自動化されたスクリプトを使用します。 これは最も簡単な方法であり、すべてのアップグレード シナリオに適用できる必要があります。
    
- **手動アップグレード。** この方法は、自動アップグレードが失敗する異常な場合のバックアップ計画として提供されます。
    
## <a name="prerequisites"></a>前提条件

アップグレードする前に、次の情報を確認してください。
  
- アクティブ リスナー証明書の拇印
    
- リスナー サービス パスワード (リスナーとすべてのエージェントのインストール時に入力)
    
- Web サイトの SSL 証明書の構成
    
## <a name="automated-upgrade"></a>自動アップグレード

スクリプトは、現在の証明書情報とリスナーパスワードを収集し、古いバージョンの製品をアンインストールしてから、製品の新しいバージョンをインストールします。 サーバーにインストールされている Redis インスタンスにはアクセスしないので、キャッシュに格納されているデータはアップグレード プロセスを通じて保持されます。
  
1. 新しいバージョンのエージェント、リスナー、Web サイトの MSI ファイルを、Update-StatsMan.ps1 スクリプトと共にリスナー コンピューター上の 1 つのフォルダーに配置します。
    
2. 管理用 PowerShell ウィンドウを開きます。 リスナー コンポーネントをアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Statistics Manager サービスのパスワードは、インストーラーに渡されるコマンド ラインにクリア テキストで表示されます。 必要に応じて、必ずモニターをシールドしてください。 
  
1. スクリプトを実行すると、製品の古いバージョンをアンインストールするように求めるメッセージが表示されます。 回答はい。
    
2. リスナー サービスが実行されている場合は、続行する前にアプリケーションを閉じる必要があります。 アプリケーションの終了を許可します (Statistics Manager リスナー サービスが停止します)。
    
3. インストール プロセスを続行します。 サービス パスワードと証明書の拇印が事前に入力されています。 設定されていない場合は、続行する前に保存した値を追加します。
    
4. 管理用 PowerShell ウィンドウを開きます。 Web サイト コンポーネントをアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. スクリプトを実行すると、製品の古いバージョンをアンインストールするように求めるメッセージが表示されます。 「はい」と答えます。
    
6. エージェント サービスが実行されている場合は、続行する前にアプリケーションを閉じる必要があります。 アプリケーションの終了を許可します (StatsMan エージェント サービスが停止します)。
    
7. インストール プロセスを続行します。 サービス パスワードと証明書の拇印が事前に入力されています。 設定されていない場合は、続行する前に保存した値を追加します。
    
8. 管理用 PowerShell ウィンドウを開きます。 エージェント コンポーネントをアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. スクリプトを実行すると、製品の古いバージョンをアンインストールするように求めるメッセージが表示されます。 回答はい。
    
10. インストール プロセスを続行します。 Web サイトのポートが事前に設定されている必要があります。 設定されていない場合は、続行する前に保存した値を追加します。
    
11. ブラウザーを使用して Web サイトが期待通り動作しているのを確認します。
    
> [!NOTE]
> エージェント アップグレードは -NoPrompt スイッチと一緒に使用できます。 これにより、アンインストール/インストール プロセスをサイレント モードで実行でき、PSExec などのツールは多数のサーバーでリモートでアップグレードを実行できます。 
  
### <a name="manual-upgrade"></a>手動アップグレード

何らかの理由で自動アップグレードが失敗した場合は、次のようにいつでも手動アップグレードを実行できます。
  
1. リスナー コンピューターで、リスナー、Web サイト、およびエージェント (このサーバーにインストールされている場合) を、次のコントロール パネルプログラムと機能アンインストールします。 
    
    > [!NOTE]
    >  アップグレード プロセスを通じてキャッシュ内のデータを維持するために、Redis をインストールした状態に維持します。
  
2. 新しいバージョンのコンポーネントをインストールします。これらのコンポーネントの入力を求めるメッセージが表示されたら、上記で保存した値も含まれます。 コンポーネントのインストールの詳細については、「Statistics Manager の展開」 [を参照してください。](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>関連情報
<a name="BKMK_Fixed"> </a>

詳細については、次のトピックを参照してください。
  
- [Skype for Business Server の Statistics Manager の計画](plan.md)
    
- [Skype for Business Server の Statistics Manager の展開](deploy.md)
    
- [Skype for Business Server の Statistics Manager のトラブルシューティング](troubleshoot.md)
