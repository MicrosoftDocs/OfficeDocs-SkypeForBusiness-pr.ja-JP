---
title: 2015 Skype for Business Serverへのアップグレード
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '概要: Lync Server 2013 から 2015 にアップグレードするSkype for Business Serverします。 Microsoft 評価センターから Skype for Business Server 2015 の無料試用版をダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 4279bb9141d896cb6aaa479f872e1684f2a3e8d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849400"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>2015 Skype for Business Serverへのアップグレード
 
**概要:** Lync Server 2013 から 2015 へのアップグレードSkype for Business Serverします。 Microsoft 評価センターから Skype for Business Server 2015 の[無料試用版をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
このドキュメントの手順を使用して、Skype for Business Server トポロジ ビルダーと新しい In-Place アップグレード機能を使用して Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。 Lync Server 2010 または Office Communications Server 2007 R2 からアップグレードする場合は、「Plan to upgrade [to Skype for Business Server 2015」を参照](../plan-your-deployment/upgrade.md)してください。

> [!NOTE]
> インプレイス アップグレードは 2015 年Skype for Business Serverでしたが、2019 年Skype for Business Serverではサポートされていません。 サイド バイ サイドの共存がサポートされています。詳細については[、「Migration to Skype for Business Server 2019」](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)を参照してください。
  
## <a name="upgrade-from-lync-server-2013"></a>Lync Server 2013 からのアップグレード

Lync Server 2013 を Skype for Business Server 2015 にアップグレードするには、前提条件ソフトウェアをインストールし、Skype for Business Server トポロジ ビルダーを使用してプール内のデータベースをアップグレードし、プールに関連付けられた各サーバーで Skype for Business Server In-Place Upgrade を使用する必要があります。 アップグレードを完了するには、このトピックの 8 つの手順を実行します。
  
### <a name="before-you-begin"></a>始める前に

- [2015 年にアップグレードする計画をSkype for Business Serverします](../plan-your-deployment/upgrade.md)。
    
- [2015 年のサーバー Skype for Business Server確認します](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- [2015 年のSkype for Business Serverインストールします](install/install-prerequisites.md)。
    
- [2015 Skype for Business Serverインストールします](install/install.md)。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>手順 1: 管理者ツールをインストールし、トポロジをダウンロードする

1. Connect Lync OCSCore または他の Lync コンポーネントがインストールされていないトポロジ内のコンピューターに接続します。
    
2. 2015 Skype for Business Serverインストール メディアから、Setup.exe\Setup\AMD64 OCS_Volume **を実行します**。  
    
3. **[インストール]** をクリックします。 
    
4. 使用許諾契約書に同意します。
    
5. 展開ウィザードで、[管理者ツールの **インストール] をクリック** し、手順に従ってインストールします。
    
     ![[管理者ツールのインストール] へのリンクが呼び出された展開ウィザードのスクリーン ショット。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. [スタートWindows] 画面で、[トポロジ ビルダー Skype for Business Server開きます。
    
7. [既存 **の展開からトポロジをダウンロードする] をクリックし**、[次へ] を **クリックします**。
    
8. トポロジの名前を入力し、[保存] を **クリックします**。
    
9. トポロジを保存した場所に移動し、トポロジのコピーを作成します。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>手順 2: トポロジ ビルダーを使用してトポロジをアップグレードして発行する

アップグレード プロセスを開始する前に、アップグレードを計画しているプールに対してすべてのサービスが実行されている必要があります。 そのため、トポロジの変更はプール内のサーバーのローカル データベースにレプリケートされます。
  
> [!IMPORTANT]
>  アップグレードする前にトポロジ ファイルのコピーを保存します。 アップグレード後、トポロジをダウングレードすることはできません。> サービスがデータベースと同じサーバー上にある場合は、常設チャット サービスが常設チャット データベースと同じサーバー上にある場合は、この手順をスキップし、手順 4 に進みます。 サービスを停止した後、各サーバーで In-Placeアップグレード セットアップを実行して、ローカル データベースをアップグレードします。
  
> [!NOTE]
> トポロジにミラーリングされたバック エンド データベースがある場合は、トポロジ ビルダーを使用してトポロジを公開すると、プリンシパル データベースとミラー 化データベースの両方が表示されます。 トポロジを公開しない場合は、トポロジを公開した後に警告が表示される場合は、すべてのデータベースがプリンシパルで実行され、ミラーではなくプリンシパルのみを選択してください。
  
2015 トポロジ ビルダーを使用して新しいトポロジをアップグレードおよび発行するには、以下のいずれかのSkype for Business Server選択します。 手順を完了し、更新されたトポロジを公開したら、このトピックの手順 3 に移動します。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>オプション 1: 分離されたフロントエンド プールと関連するアーカイブストアと監視ストアをアップグレードする

アップグレードするプールにアーカイブ ストアと監視ストアの依存関係がある場合は、次の手順を使用すると、アーカイブ ストアと監視ストアもアップグレードされます。
  
1. トポロジ ビルダーで、Lync Server 2013 プールを右クリックし、[アップグレードして **2015 年 2015** 年Skype for Business Server選択し、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションを使用した右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. トポロジ ビルダーで、[アクション発行]**トポロジまたは [** アクション  >  **トポロジの発行**  >  **] を**  >  **クリックします**。 
    
     ![トポロジ ビルダーの [トポロジの発行] オプションを使用した [アクション] メニューのスクリーン ショット。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 発行中に、アーカイブおよび監視ストアにデータベースをインストールします。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>オプション 2: アーカイブ ストアと監視ストアをアップグレードせずにフロントエンド プールをアップグレードする

次の手順を使用すると、選択したプールのアーカイブと監視が無効になります。 プールには、アップグレード後にアーカイブストアと監視ストアが含めらなされます。
  
1. トポロジ ビルダーで、アップグレードする Lync Server 2013 プールを選択します。
    
2. Lync Server 2013 のアーカイブおよび監視ストアへの依存関係を削除します。 
    
   - [アクションの編集 **]**  >  **プロパティに移動します**。
    
   - [アーカイブ **] チェック ボックスを** オフにします。
    
     ![[プロパティの編集] ダイアログ ボックスの [アーカイブ] チェック ボックスのスクリーン ショット。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - [監視] **チェック ボックス** をオフにします。
    
     ![[監視] チェック ボックスを表示する [プロパティの編集] ダイアログ ボックスのスクリーン ショット。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 プールを右クリックし、[アップグレード **して 2015** 年Skype for Business Serverを選択し、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションを使用した右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. トポロジ ビルダーで、[アクション発行]**トポロジまたは [** アクション  >  **トポロジの発行**  >  **] を**  >  **クリックします**。 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>オプション 3: フロントエンド プールをアップグレードし、2015 アーカイブおよび監視ストアSkype for Business Serverに関連付け

次の手順を使用すると、アーカイブと監視は前のストアで停止し、作成した新しいストアで開始されます。 
  
1. トポロジ ビルダーで、アップグレードする Lync Server 2013 プールを選択します。 
    
2. Lync Server 2013 のアーカイブおよび監視ストアへの依存関係を削除します。 
    
   - [アクションの編集 **]**  >  **プロパティに移動します**。
    
   - [アーカイブ **] チェック ボックスを** オフにします。
    
     ![[プロパティの編集] ダイアログ ボックスの [アーカイブ] チェック ボックスのスクリーン ショット。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - [監視] **チェック ボックス** をオフにします。
    
     ![[監視] チェック ボックスを表示する [プロパティの編集] ダイアログ ボックスのスクリーン ショット。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 プールを右クリックし、[アップグレード **して 2015** 年Skype for Business Serverを選択し、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションを使用した右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. アーカイブ用の新SQLストアを作成します。 
    
   - プールとアクション編集 **のプロパティ**  >  **を選択します**。 
    
   -  [アーカイブ **] チェック ボックス** をオンにします。
    
   - **[新規作成]** をクリックします。
    
     ![[アーカイブ] セクションの [新しい] ボタンを表示する [プロパティの編集] ダイアログ のスクリーン ショット。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 監視用の新SQLストアを作成します。 
    
   - プールとアクション編集 **のプロパティ**  >  **を選択します**。 
    
   -  [監視] **チェック ボックス** をオンにします。
    
   - **[新規作成]** をクリックします。
    
     ![[監視] セクションの [新しい] ボタンを表示する [プロパティの編集] ダイアログ のスクリーン ショット。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. トポロジ ビルダーで、[アクション発行]**トポロジまたは [** アクション  >  **トポロジの発行**  >  **] を**  >  **クリックします**。 
    
7. 発行中に、新しいアーカイブおよび監視ストアにデータベースをインストールします。
    
### <a name="step-3-wait-for-replication"></a>手順 3: レプリケーションを待機する

更新されたトポロジを環境内のすべてのサーバーに公開するために、レプリケーションに時間を与えます。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>手順 4: アップグレードするプール内のすべてのサービスを停止する

アップグレードするプールをサービスしている各サーバーで、PowerShell で次のコマンドレットを実行します。
  
```powershell
Disable-CsComputer -Scorch
```

アップグレード プロセス中にDisable-CsComputer再起動する必要がある場合がある場合がありますIn-Place使用することをお勧めします。 Stop-CsWindowsService を使用する場合、一部のサービスは再起動後に自動的に再起動する場合があります。 これにより、アップグレードIn-Place失敗する可能性があります。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>手順 5: フロントエンド プールとフロント エンド 以外のプール サーバーをアップグレードする

> [!NOTE]
>  アップグレードを行う前に、Skype for Business Server 2015 に必要なすべての新しい前提条件をインストールしてください。アップグレードを試みる前に、> 以上の空き領域が含まれます。 さらに、ドライブが固定ローカル ドライブである必要があります。 USB または Firewire で接続されていない、NTFS ファイル システムで書式設定されている、圧縮されていない、およびページ ファイル.> PowerShell バージョン 6.2.9200.0 以降が含まれます。> 最新の Lync Server 2013 累積的な更新プログラムがインストールされています。> SQL Server 2012 SP1 がインストールされています。> Microsoft Update を使用する場合は、次の KB が自動的にインストールされます。> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
各サーバーIn-Placeアップグレードを使用して、フロントエンド プール、エッジ プール、仲介サーバー、および常設チャット プールを更新します。
  
1. 各サーバーで **、Setup.exe** 2015 OCS_Volume メディアの **OCS_Volume\Setup\amd64** からSkype for Business Server実行します。
    
2. 使用許諾契約書に同意し、[アップグレード] の指示にIn-Placeします。
    
3. フロント エンド プール内の各サーバーと、フロント エンド 以外のプール サーバーごとに、これらの手順を繰り返します。
    
> [!NOTE]
> アップグレード中にサーバーを再起動するように求In-Place場合があります。 いいですよ。 再起動後、アップグレードIn-Placeがオフの場所から続行されます。 
  
アップグレードがIn-Place完了すると、次のメッセージが表示されます。
  
![一時アップグレードが正常に完了したと表示されるスクリーン ショット。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>手順 6: アップグレードされたサーバーすべてでサービスを再起動する

> [!NOTE]
> サービスを再起動する前に、%ProgramData%\WindowsFabric がすべてのフロント エンド サーバーに存在しないか確認してください。 存在する場合は、サービスを開始する前に削除してください。 
  
- フロントエンド プール内のすべてのサーバーをアップグレードしたら、次の PowerShell コマンドを使用してサービスを再起動します。 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > In-Place Upgrade の実行を開始する前に既に保留中のシステム再起動が必要な場合、In-Place Upgrade はインストールの最後に再起動を要求しません。 これにより、このコマンドレットを使用してサービスを開始しようとするときに、最初のフロントエンド サーバーに対していくつかのアセンブリ例外がスローStart-CSPoolされます。 これらのエラーを解決するには、プール内のすべてのサーバーを再起動し、コマンドレットを再度実行します。 
  
- フロント エンド 以外のプール サーバーで、次のコマンドを使用してサービスを再起動します。
    
  ```powershell
  Start-CsWindowsService
  ```

[アップグレード] **ページで [OK]** In-Placeすると、この手順を完了するために次のリマインダーが表示されます。
  
![インプレイス アップグレードが正常に完了した後の次の手順を示すスクリーン ショット。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>手順 7: 機能Skype for Business確認する

アップグレードが成功したのを確認するには、アップグレードされたプールについて、Skype for Business機能が正常に動作している必要があります。 
  
### <a name="step-8-upgrade-secondary-pools"></a>手順 8: セカンダリ プールをアップグレードする

環境に追加のプールをアップグレードするには、このトピックの手順を繰り返します。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>アップグレードに関するIn-Placeトラブルシューティング

アップグレードがIn-Place場合、次の図のようなメッセージが表示されることがあります。 
  
![必要な累積的な更新プログラムがインストールされていないため、インプレイス アップグレードが失敗したと表示されるスクリーン ショット。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
ページの下部にある完全なメッセージを確認して、問題のトラブルシューティングに役立ちます。 [ログ **の表示] をクリック** して詳細を取得します。
  
アップグレード準備の確認または不足している前提条件のインストールで In-Place アップグレードが失敗した場合は、サーバーに最新の Windows Server、Lync Server、および SQL Server 更新プログラムが適用され、必要なすべてのソフトウェアと役割がインストールされていることを確認します。 必要な情報の一覧については、「サーバー要件 for [Skype for Business Server 2015」](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)および「Install prerequisites for Skype for Business Server [2015」を参照](install/install-prerequisites.md)してください。
  
## <a name="see-also"></a>関連項目

[2015 年にアップグレードSkype for Business Serverする](../plan-your-deployment/upgrade.md)
  
[2015 年のサーバー Skype for Business Server要件](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[2015 年Skype for Business Serverインストールする](install/install-prerequisites.md)
  
[インストール Skype for Business Server 2015](install/install.md)
