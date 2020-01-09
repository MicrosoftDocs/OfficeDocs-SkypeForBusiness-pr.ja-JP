---
title: Skype for Business Server の Statistics Manager のアップグレード
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: '概要: Skype for Business Server の統計マネージャーをアップグレードする方法については、このトピックを参照してください。'
ms.openlocfilehash: de88257b628256c47b68036852d82fb6715c043f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992504"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server の Statistics Manager のアップグレード
 
**概要:** このトピックでは、Skype for Business Server の統計マネージャーをアップグレードする方法について説明します。
  
このトピックでは、Skype for Business Server の統計マネージャーの既存のインストールをアップグレードする方法について説明します。 Skype for business Server の正常性とパフォーマンスデータをリアルタイムで表示できる強力なツールです。 数秒ごとに数百のサーバーのパフォーマンス データをポーリングでき、その結果をすぐに統計情報 マネージャーのウェブ サイト上に表示することができます。 
  
統計マネージャーとリリース2.0 の新機能の詳細については、「Skype for business [server の統計情報マネージャーの計画](plan.md)」および「 [Skype for Business Server の統計マネージャーの展開](deploy.md)」を参照してください。
  
アップグレードには、以下の 2 つの異なる方法があります。
  
- **自動アップグレード**。 このメソッドは、自動化されたスクリプトを使います。 これは最も簡単な方法です。すべてのアップグレードシナリオに適用する必要があります。
    
- **手動アップグレード**。 この方法は、通常、自動アップグレードが失敗した場合にバックアップ計画として提供されます。
    
## <a name="prerequisites"></a>前提条件

アップグレードする前に、以下の情報を用意する必要があります。
  
- アクティブなリスナーの証明書の拇印
    
- リスナー サービスのパスワード (リスナーおよび各エージェントのインストール時に入力)
    
- Web サイトの SSL 証明書の構成
    
## <a name="automated-upgrade"></a>自動アップグレード

このスクリプトでは、使用している現在の証明書情報およびリスナー パスワードが収集され、製品の古いバージョンをアンインストールした後、製品の新しいバージョンがインストールされます。 サーバーにインストールされている Redis インスタンスは関与しないため、キャッシュに格納されているデータはすべてアップグレードの間も保持されます。
  
1. 新しいバージョンのエージェント、リスナー、web サイトの MSI ファイルを Update-StatsMan スクリプトと共に、リスナーコンピューター上の1つのフォルダーに配置します。
    
2. 管理用の PowerShell ウィンドウを開きます。 リスナーのコンポーネントを、以下の手順でアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> 統計情報マネージャーサービスのパスワードは、インストーラーに渡されるときに、コマンドラインのクリアテキストで表示されます。 必要に応じて、使用しているディスプレイの画面を隠すようにしてください。 
  
1. スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。 「Yes (はい)」と答えます。
    
2. リスナー サービスが実行中の場合、継続する前にこのアプリケーションを閉じるかどうか確認するメッセージが表示されます。 アプリケーションを閉じることを許可します (統計マネージャーリスナーサービスは停止します)。
    
3. インストール プロセスを継続します。 サービス パスワードと証明書の拇印があらかじめ入力されていることに注意してください。 入力されていない場合は、継続する前に保存した値を追加します。
    
4. 管理用の PowerShell ウィンドウを開きます。 Web サイト コンポーネントを、以下の手順でアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。 「Yes (はい)」と答えます。
    
6. エージェント サービスが実行中の場合、継続する前にこのアプリケーションを閉じるかどうか確認するメッセージが表示されます。 このアプリケーションを閉じることを許可します (StatsMan エージェント サービスが停止します)。
    
7. インストール プロセスを継続します。 サービス パスワードと証明書の拇印があらかじめ入力されていることに注意してください。 入力されていない場合は、継続する前に保存した値を追加します。
    
8. 管理用の PowerShell ウィンドウを開きます。 エージェント コンポーネントを、以下の手順でアップグレードします。
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。 「Yes (はい)」と答えます。
    
10. インストール プロセスを継続します。 Web サイトのポートがあらかじめ入力されていることに注意してください。 入力されていない場合は、継続する前に保存した値を追加します。
    
11. ブラウザーを使用して、Web サイトが期待したとおりに機能することを確認します。
    
> [!NOTE]
> エージェントのアップグレードでは、-NoPrompt スイッチを使用できます。 このスイッチを使用すると、アンインストール プロセスやインストール プロセスでのメッセージの確認が省略でき、PSExec などのツールを使用して大量のサーバーのアップグレードをリモートで実行できます。 
  
### <a name="manual-upgrade"></a>手動アップグレード

何らかの理由で自動アップグレードが失敗する場合、いつでも手動アップグレードを以下の手順で実行できます。
  
1. 	リスナーのコンピューターで、リスナー、Web サイト、およびエージェント (このエージェントがこのサーバーにインストールされている場合) を [プログラムと機能] コントロール パネルを使用してアンインストールします。 
    
    > [!NOTE]
    >   アップグレード プロセスを通して Redis のキャッシュ内のデータを維持できるように、Redis をインストールしたままにしておきます。
  
2. 	上記の手順で値の保存の確認メッセージが表示されたときに保存した値を含め、コンポーネントの新しいバージョンをインストールします。コンポーネントのインストールの詳細については、「[Statistics Manager の展開](deploy.md#BKMK_Deploy)」を参照してください。

    
## <a name="for-more-information"></a>関連情報
<a name="BKMK_Fixed"> </a>

詳細については、以下を参照してください。
  
- [Skype for Business Server の Statistics Manager の計画](plan.md)
    
- [Skype for Business Server の Statistics Manager の展開](deploy.md)
    
- [Skype for Business Server の Statistics Manager のトラブルシューティング](troubleshoot.md)
