---
title: Skype for Business Server 2015 にアップグレードする
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: '概要: Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について説明します。'
ms.openlocfilehash: 30cd73e8c21c9ee60521e1c2bddf8bddf4d23b6f
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860572"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 にアップグレードする
 
**概要：** Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について説明します。 
  
このドキュメントの手順を使用して、Skype for Business Server トポロジ ビルダーと新しい In-Place アップグレード機能を使用して Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。 Lync Server 2010 または Office Communications Server 2007 R2 からアップグレードする場合は、「[Skype for Business Server 2015 にアップグレードする計画](../plan-your-deployment/upgrade.md)」を参照してください。

> [!NOTE]
> インプレース アップグレードは 2015 Skype for Business Serverで利用できましたが、2019 Skype for Business Serverではサポートされなくなりました。 並行共存がサポートされています。詳細については、「[Skype for Business Server 2019 への移行](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)」を参照してください。
  
## <a name="upgrade-from-lync-server-2013"></a>Lync Server 2013 からのアップグレード

Lync Server 2013 を 2015 Skype for Business Serverにアップグレードするには、前提条件となるソフトウェアをインストールし、Skype for Business Server トポロジ ビルダーを使用してプール内のデータベースをアップグレードし、関連する各サーバーでSkype for Business Server In-Placeアップグレードを使用する必要があります。プールを指定します。 アップグレードを完了するには、このトピックの 8 つの手順を実行します。
  
### <a name="before-you-begin"></a>はじめに

- [Skype for Business Server 2015 にアップグレードする計画](../plan-your-deployment/upgrade.md)を確認します。
    
- [Skype for Business Server 2015 のサーバー要件を確認します](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- [Skype for Business Server 2015 の前提条件をインストール](install/install-prerequisites.md)します。
    
- [Skype for Business Server 2015 をインストールします](install/install.md)。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>手順 1: 管理者ツールをインストールし、トポロジをダウンロードする

1. Lync OCSCore またはその他の Lync コンポーネントがインストールされていないトポロジ内のコンピューターにConnectします。
    
2. Skype for Business Server 2015 インストール メディアから、**OCS_Volume\Setup\AMD64 からSetup.exeを実行します**。**** 
    
3. **[インストール]** をクリックします。 
    
4. 使用許諾契約書に同意します。
    
5. 展開ウィザードで、[ **管理者ツールのインストール**] をクリックし、手順に従ってインストールします。
    
     ![展開ウィザードのスクリーン ショットと、管理者ツールのインストールへのリンクが呼び出されました。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Windows スタート画面から、トポロジ ビルダー Skype for Business Server開きます。
    
7. **[既存のデプロイからトポロジをダウンロードする**] をクリックし、[**次へ**] をクリックします。
    
8. トポロジの名前を入力し、[ **保存]** をクリックします。
    
9. トポロジを保存した場所に移動し、トポロジのコピーを作成します。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>手順 2: トポロジ ビルダーを使用してトポロジをアップグレードして発行する

アップグレード プロセスを開始する前に、アップグレードする予定のプールに対してすべてのサービスが実行されている必要があります。 これにより、トポロジの変更がプール内のサーバーのローカル データベースにレプリケートされます。
  
> [!IMPORTANT]
>  アップグレードする前に、トポロジ ファイルのコピーを保存します。 アップグレード後は、トポロジをダウングレードできません。> 常設チャット サービスが常設チャット データベースと同じサーバー上にあるような、データベースと同じサーバー上にある場合は、この手順をスキップし、手順 4 に進みます。 サービスを停止したら、各サーバーでIn-Placeアップグレードセットアップを実行してローカル データベースをアップグレードします。
  
> [!NOTE]
> トポロジにミラー化されたバックエンド データベースがある場合は、トポロジ ビルダーを使用して **トポロジを発行すると** 、プリンシパル データベースとミラー化されたデータベースの両方が表示されます。 すべてのデータベースがプリンシパルで実行されていることを確認し、ミラーではなくプリンシパルのみを選択します。それ以外の場合は、トポロジを発行した後に警告が表示されます。
  
Skype for Business Server 2015 トポロジ ビルダーを使用して新しいトポロジをアップグレードして発行するには、次のいずれかのオプションを選択します。 手順を完了し、更新されたトポロジを公開したら、このトピックの手順 3 に進みます。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>オプション 1: 分離されたフロントエンド プールと関連するアーカイブ ストアと監視ストアをアップグレードする

アップグレードするプールにアーカイブ ストアと監視ストアの依存関係がある場合は、次の手順を使用すると、アーカイブ ストアと監視ストアもアップグレードされます。
  
1. トポロジ ビルダーで、Lync Server 2013 プールを右クリックし、**Skype for Business Server 2015 にアップグレードを** 選択し、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションを使用した右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. トポロジ ビルダーで、[**アクション** > **の発行] トポロジ** または **[アクション****トポロジ** > **の発行**]  >  をクリックします。 
    
     ![トポロジ ビルダーの [公開トポロジ] オプションを使用した [アクション] メニューのスクリーン ショット。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 発行中に、アーカイブと監視ストアにデータベースをインストールすることを選択します。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>オプション 2: アーカイブ ストアと監視ストアをアップグレードせずにフロント エンド プールをアップグレードする

次の手順を使用すると、選択したプールのアーカイブと監視が無効になります。 アップグレード後、プールにアーカイブ ストアと監視ストアはありません。
  
1. トポロジ ビルダーで、アップグレードする Lync Server 2013 プールを選択します。
    
2. Lync Server 2013 アーカイブ ストアと監視ストアへの依存関係を削除します。 
    
   - Action **Edit プロパティ** に移動 **します** > 。
    
   - **[アーカイブ**] チェック ボックスをオフにします。
    
     ![[プロパティの編集] ダイアログ ボックスの [アーカイブ] チェック ボックスのスクリーン ショット。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - **[監視**] チェック ボックスをオフにします。
    
     ![[監視] チェック ボックスを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 プールを右クリックし、**Skype for Business Server 2015 へのアップグレード** を選択し、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションを使用した右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. トポロジ ビルダーで、[**アクション** > **の発行] トポロジ** または **[アクション****トポロジ** > **の発行**]  >  をクリックします。 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>オプション 3: フロント エンド プールをアップグレードし、新しい Skype for Business Server 2015 アーカイブ ストアと監視ストアに関連付ける

次の手順を使用すると、アーカイブと監視は前のストアで停止し、作成した新しいストアで開始されます。 
  
1. トポロジ ビルダーで、アップグレードする Lync Server 2013 プールを選択します。 
    
2. Lync Server 2013 アーカイブ ストアと監視ストアへの依存関係を削除します。 
    
   - Action **Edit プロパティ** に移動 **します** > 。
    
   - **[アーカイブ**] チェック ボックスをオフにします。
    
     ![[プロパティの編集] ダイアログ ボックスの [アーカイブ] チェック ボックスのスクリーン ショット。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - **[監視**] チェック ボックスをオフにします。
    
     ![[監視] チェック ボックスを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 プールを右クリックし、**Skype for Business Server 2015 へのアップグレード** を選択し、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションを使用した右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. アーカイブ用の新しいSQL ストアを作成します。 
    
   - プールと **アクション** > **編集のプロパティ** を選択します。 
    
   -  [アーカイブ] チェック ボックス **を** オンにします。
    
   - **[新規作成]** をクリックします。
    
     ![[アーカイブ] セクションの [新規] ボタンを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 監視用の新しいSQL ストアを作成します。 
    
   - プールと **アクション** > **編集のプロパティ** を選択します。 
    
   -  [ **監視** ] チェック ボックスをオンにします。
    
   - **[新規作成]** をクリックします。
    
     ![[監視] セクションの [新規] ボタンを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. トポロジ ビルダーで、[**アクション** > **の発行] トポロジ** または **[アクション****トポロジ** > **の発行**]  >  をクリックします。 
    
7. 発行中に、新しいアーカイブ および監視ストアにデータベースをインストールすることを選択します。
    
### <a name="step-3-wait-for-replication"></a>手順 3: レプリケーションを待機する

更新されたトポロジを環境内のすべてのサーバーに公開する時間をレプリケーションに与えます。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>手順 4: アップグレードするプール内のすべてのサービスを停止する

アップグレードするプールにサービスを提供している各サーバーで、PowerShell で次のコマンドレットを実行します。
  
```powershell
Disable-CsComputer -Scorch
```

In-Placeアップグレード プロセス中にサーバーを再起動する必要がある場合があるため、Disable-CsComputerを使用することをお勧めします。 Stop-CsWindowsService を使用する場合、再起動後に一部のサービスが自動的に再起動することがあります。 これにより、In-Placeのアップグレードが失敗する可能性があります。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>手順 5: フロント エンド プールとフロント エンド 以外のプール サーバーをアップグレードする

> [!NOTE]
>  アップグレードする前に、Skype for Business Server 2015 に必要なすべての新しい前提条件をインストールしてください。これには、アップグレードを試行する前に 32 GB 以上の空き領域が>含まれます。 さらに、ドライブが固定ローカル ドライブであることを確認します。 は USB または Firewire で接続されておらず、NTFS ファイル システムでフォーマットされており、圧縮されておらず、PowerShell バージョン 6.> PowerShell バージョン 6.2.9200.0 以降が含まれていません。> 最新の Lync Server 2013 累積更新プログラムがインストールされています。> SQL Server 2012 SP1 がインストール>次の KB がインストールされます (Microsoft Update を使用する場合は、自動的にインストールされます)。> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
各サーバーでIn-Placeアップグレードを使用して、フロントエンド プール、エッジ プール、仲介サーバー、常設チャット プールを更新します。
  
1. 各サーバーで、**Skype for Business Server** 2015 インストール メディア **で OCS_Volume\Setup\amd64** からSetup.exeを実行します。
    
2. 使用許諾契約書に同意し、In-Placeアップグレードのプロンプトに従います。
    
3. フロントエンド プール内の各サーバーと、フロント エンド 以外の各プール サーバーで、これらの手順を繰り返します。
    
> [!NOTE]
> In-Placeアップグレード中にサーバーの再起動を求めるメッセージが表示される場合があります。 いいですよ。 再起動すると、In-Placeアップグレードは中断した場所から続行されます。 
  
In-Placeアップグレードが正常に完了すると、次のメッセージが表示されます。
  
![インプレース アップグレードが正常に完了したことを示すスクリーン ショット。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>手順 6: アップグレードされたすべてのサーバーでサービスを再起動する

> [!NOTE]
> サービスを再起動する前に、%ProgramData%\WindowsFabric がすべてのフロント エンド サーバーに存在しないことを確認してください。 存在する場合は、サービスを開始する前に削除します。 
  
- フロントエンド プール内のすべてのサーバーをアップグレードしたら、次の PowerShell コマンドを使用してサービスを再起動します。 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > In-Place アップグレードの実行を開始する前にシステムの再起動が既に必要な場合、In-Placeアップグレードではインストールの終了時に再起動を求められません。 これにより、Start-CSPool コマンドレットを使用してサービスを開始しようとすると、最初のフロントエンド サーバーに対していくつかのアセンブリ例外がスローされます。 これらのエラーを解決するには、プール内のすべてのサーバーを再起動し、コマンドレットをもう一度実行します。 
  
- フロント エンド 以外のプール サーバーで、次のコマンドを使用してサービスを再起動します。
    
  ```powershell
  Start-CsWindowsService
  ```

In-Placeアップグレード ページで **[OK] を** クリックすると、この手順を完了するための次のリマインダーが表示されます。
  
![インプレース アップグレードが正常に完了した後の次の手順を示すスクリーン ショット。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>手順 7: Skype for Business機能が機能することを確認する

アップグレードが成功したことを確認するには、アップグレードされたプールについて、Skype for Businessをテストして、機能が期待どおりに機能していることを確認します。 
  
### <a name="step-8-upgrade-secondary-pools"></a>手順 8: セカンダリ プールをアップグレードする

このトピックの手順を繰り返して、環境内に追加のプールをアップグレードします。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>In-Placeアップグレードに関する問題のトラブルシューティング

In-Placeアップグレードに失敗した場合は、次の図のようなメッセージが表示される場合があります。 
  
![必要な累積的な更新プログラムがインストールされていないため、インプレース アップグレードが失敗したことを示すスクリーン ショット。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
問題のトラブルシューティングに役立つ、ページの下部にある完全なメッセージを確認します。 [ **ログの表示** ] をクリックして詳細を取得します。
  
アップグレードの **準備の確認** または **不足している前提条件のインストール** でIn-Placeアップグレードが失敗した場合は、サーバーに最新のWindows Server、Lync Server、およびSQL Server更新プログラムがすべて適用されていることを確認し、必要なすべてのソフトウェアとロールがインストールされていることを確認します。 必要なものの一覧については、「[Skype for Business Server 2015 のサーバー要件](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」と「[Skype for Business Server 2015 のインストールの前提条件](install/install-prerequisites.md)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 にアップグレードする予定](../plan-your-deployment/upgrade.md)
  
[Skype for Business Server 2015 のサーバー要件](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の前提条件をインストールする](install/install-prerequisites.md)
  
[Skype for Business Server 2015 をインストールする](install/install.md)
