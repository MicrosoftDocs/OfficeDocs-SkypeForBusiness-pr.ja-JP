---
title: Skype for Business Server 2015 へのアップグレード
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '概要: Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について学習します。 Microsoft Evaluation Center から Skype for Business Server 2015 の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820427"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 へのアップグレード
 
**概要:** Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について学習します。 Microsoft Evaluation Center から Skype for Business Server 2015 の無料試用版  [をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
このドキュメントの手順を使用して、Skype for Business Server トポロジ ビルダーと新しい In-Place アップグレード機能を使用して Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。 Lync Server 2010 または Office Communications Server 2007 R2 からアップグレードする場合は [、「Skype for Business Server 2015](../plan-your-deployment/upgrade.md)へのアップグレードを計画する」を参照してください。

> [!NOTE]
> 一時アップグレードは Skype for Business Server 2015 で利用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 共存がサポートされている場合は [、「Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) への移行」を参照してください。
  
## <a name="upgrade-from-lync-server-2013"></a>Lync Server 2013 からのアップグレード

Lync Server 2013 を Skype for Business Server 2015 にアップグレードするには、前提条件となるソフトウェアをインストールし、Skype for Business Server トポロジ ビルダーを使用してプール内のデータベースをアップグレードし、プールに関連付けられている各サーバーで Skype for Business Server In-Place アップグレードを使用する必要があります。 アップグレードを完了するには、このトピックの 8 つの手順を実行します。
  
### <a name="before-you-begin"></a>はじめに

- [Review Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).
    
- [Skype for Business Server 2015 のサーバー要件を確認します](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- [Skype for Business Server 2015 の前提条件をインストールします](install/install-prerequisites.md) 。
    
- [Skype for Business Server 2015 をインストールします](install/install.md) 。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>手順 1: 管理者ツールをインストールしてトポロジをダウンロードする

1. Lync OCSCore または他の Lync コンポーネントがインストールされていないトポロジ内のコンピューターに接続します。
    
2. Skype for Business Server 2015インストール メディアから **、Setup.exe\Setup\AMD64 OCS_Volumeを実行します**。 
    
3. **[インストール]** をクリックします。 
    
4. 使用許諾契約書に同意します。
    
5. 展開ウィザードで、[管理者ツールのインストール] **をクリック** し、手順に従ってインストールします。
    
     ![[Install Administrator Tools] (インストール管理者ツール) へのリンクが示された展開ウィザードのスクリーン ショット。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Windows のスタート画面で、Skype for Business Server トポロジ ビルダーを開きます。
    
7. [ **既存の展開からトポロジをダウンロード] をクリックし、[** 次へ] を **クリックします**。
    
8. トポロジの名前を入力し、[保存] をクリック **します**。
    
9. トポロジを保存した場所に移動し、トポロジのコピーを作成します。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>手順 2: トポロジ ビルダーを使用してトポロジをアップグレードおよび公開する

アップグレード プロセスを開始する前に、アップグレードを計画しているプールに対してすべてのサービスが実行されている必要があります。 そのため、トポロジの変更はプール内のサーバーのローカル データベースにレプリケートされます。
  
> [!IMPORTANT]
>  アップグレードする前に、トポロジ ファイルのコピーを保存します。 アップグレード後は、トポロジをダウングレードできません。> 常設チャット サービスが常設チャット データベースと同じサーバー上にあるなど、サービスがデータベースと同じサーバーにある場合は、この手順をスキップして、手順 4. に進みます。 サービスを停止した後、各サーバーで In-Place アップグレード のセットアップを実行して、ローカル データベースをアップグレードします。
  
> [!NOTE]
> トポロジにミラー化されたバック エンド データベースがある場合、トポロジ ビルダーを使用してトポロジを公開すると、プリンシパル データベースとミラー 化データベースの両方が表示されます。 すべてのデータベースがプリンシパルで実行され、ミラーではなくプリンシパルのみを選択してください。そうしないと、トポロジの公開後に警告が表示されます。
  
Skype for Business Server 2015 トポロジ ビルダーを使用して新しいトポロジをアップグレードおよび公開するには、以下のいずれかのオプションを選択します。 手順を完了し、更新されたトポロジを公開したら、このトピックの手順 3 に進みます。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>オプション 1: 分離されたフロントエンド プールと関連するアーカイブストアと監視ストアをアップグレードする

アップグレードするプールにアーカイブ ストアと監視ストアの依存関係がある場合は、次の手順を使用すると、アーカイブ ストアと監視ストアもアップグレードされます。
  
1. トポロジ ビルダーで、Lync Server 2013 プールを右クリックし **、[Skype for Business Server 2015** へのアップグレード] を選択して、手順を実行します。 
    
     ![Lync Server 2013 のアップグレード オプションを含む右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. トポロジ ビルダーで、[アクションの公開 **]**  >  **トポロジまたは [アクション****トポロジの公開]**  >  **を**  >  **クリックします**。 
    
     ![トポロジ ビルダーの [トポロジの公開] オプションが表示された [操作] メニューのスクリーン ショット。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 発行時に、アーカイブストアと監視ストアにデータベースをインストールします。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>オプション 2: アーカイブ ストアと監視ストアをアップグレードせずにフロントエンド プールをアップグレードする

次の手順を使用すると、選択したプールのアーカイブと監視が無効になります。 アップグレード後、プールにはアーカイブ ストアと監視ストアは含めらなされます。
  
1. トポロジ ビルダーで、アップグレードする Lync Server 2013 プールを選択します。
    
2. Lync Server 2013 のアーカイブ ストアと監視ストアへの依存関係を削除します。 
    
   - [アクションの編集 **]**  >  **プロパティに移動します**。
    
   - [アーカイブ **] チェック ボックスを** オフにします。
    
     ![[プロパティの編集] ダイアログ ボックスの [アーカイブ] チェック ボックスのスクリーン ショット。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - [監視] **チェック ボックス** をオフにします。
    
     ![[監視] チェック ボックスを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 プールを右クリックし **、[Skype for Business Server 2015** へのアップグレード] を選択して、手順を実行します。 
    
     ![Lync Server 2013 のアップグレード オプションを含む右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. トポロジ ビルダーで、[アクションの公開 **]**  >  **トポロジまたは [アクション****トポロジの公開]**  >  **を**  >  **クリックします**。 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>オプション 3: フロント エンド プールをアップグレードし、それを新しい Skype for Business Server 2015 のアーカイブおよび監視ストアに関連付にする

次の手順を実行すると、アーカイブと監視は前のストアで停止し、作成した新しいストアで開始されます。 
  
1. トポロジ ビルダーで、アップグレードする Lync Server 2013 プールを選択します。 
    
2. Lync Server 2013 のアーカイブ ストアと監視ストアへの依存関係を削除します。 
    
   - [アクションの編集 **]**  >  **プロパティに移動します**。
    
   - [アーカイブ **] チェック ボックスを** オフにします。
    
     ![[プロパティの編集] ダイアログ ボックスの [アーカイブ] チェック ボックスのスクリーン ショット。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - [監視] **チェック ボックス** をオフにします。
    
     ![[監視] チェック ボックスを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 プールを右クリックし **、[Skype for Business Server 2015** へのアップグレード] を選択して、手順を実行します。 
    
     ![Lync Server 2013 のアップグレード オプションを含む右クリック メニューのスクリーン ショット。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. アーカイブ用の新SQLストアを作成します。 
    
   - プールとアクション編集の **プロパティ**  >  **を選択します**。 
    
   -  [アーカイブ **] チェック ボックスを** オンにします。
    
   - **[新規作成]** をクリックします。
    
     ![[アーカイブ] セクションの [新規] ボタンを表示する [プロパティの編集] ダイアログのスクリーン ショット。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 監視用の新SQLストアを作成します。 
    
   - プールとアクション編集の **プロパティ**  >  **を選択します**。 
    
   -  [監視] **チェック ボックス** をオンにします。
    
   - **[新規作成]** をクリックします。
    
     ![[監視] セクションの下に [新規] ボタンが表示される [プロパティの編集] ダイアログのスクリーン ショット。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. トポロジ ビルダーで、[アクションの公開 **]**  >  **トポロジまたは [アクション****トポロジの公開]**  >  **を**  >  **クリックします**。 
    
7. 発行時に、新しいアーカイブおよび監視ストアにデータベースをインストールします。
    
### <a name="step-3-wait-for-replication"></a>手順 3: レプリケーションを待つ

更新されたトポロジを環境内のすべてのサーバーに公開するために、レプリケーションに時間を与えます。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>手順 4: アップグレードするプール内のすべてのサービスを停止する

アップグレードするプールを提供している各サーバーで、PowerShell で次のコマンドレットを実行します。
  
```powershell
Disable-CsComputer -Scorch
```

アップグレード プロセスのDisable-CsComputerサーバーの再起動が必要になる場合がある場合は、このIn-Place使用することをお勧めします。 Stop-CsWindowsService を使用すると、再起動後に一部のサービスが自動的に再起動される場合があります。 この場合、アップグレードIn-Place失敗する可能性があります。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>手順 5: フロントエンド プールとフロントエンド 以外のプール サーバーをアップグレードする

> [!NOTE]
>  アップグレードの前に、Skype for Business Server 201 > 5 に必要なすべての新しい前提条件をインストールしてください。この前提条件には、アップグレードを試行する前に、32 GB 以上の空き領域が含まれます。 また、ドライブが固定ローカル ドライブで、USB または Firewire で接続されていないか確認してください。 は NTFS ファイル システムでフォーマットされ、圧縮されません。ページ ファイルは含> PowerShell バージョン 6. 2.9200.0 以降.> 最新の Lync Server 2013 累積更新プログラムがインストールされている。> SQL Server 2012 SP1 がインストールされている。> 次の KB がインストールされている (Microsoft Update を使用している場合は自動的にインストール):> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB29820066](https://support.microsoft.com/kb/2982006)
  
各サーバーIn-Placeアップグレードを使用して、フロントエンド プール、エッジ プール、仲介サーバー、および常設チャット プールを更新します。
  
1. 各サーバーで、skype for Business Server 2015 **Setup.exe** メディアで **OCS_Volume\Setup\amd64** からこのコマンドを実行します。
    
2. 使用許諾契約書に同意し、アップグレードの指示にIn-Placeします。
    
3. フロント エンド プール内の各サーバーと、フロントエンド 以外のプール サーバーごとに、これらの手順を繰り返します。
    
> [!NOTE]
> アップグレード中にサーバーを再起動するように求In-Placeがあります。 いいですよ。 再起動後、アップグレードIn-Place、アップグレードがオフにされた場所から続行されます。 
  
アップグレードIn-Place正常に完了すると、次のメッセージが表示されます。
  
![一時アップグレードが正常に完了した場合のスクリーン ショット。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>手順 6: アップグレードされたサーバーすべてでサービスを再起動する

> [!NOTE]
> サービスを再起動する前に、%ProgramData%\WindowsFabric がすべてのフロントエンド サーバーに存在しないか確認してください。 存在する場合は、サービスを開始する前に削除します。 
  
- フロントエンド プール内のすべてのサーバーをアップグレードした後、次の PowerShell コマンドを使用してサービスを再起動します。 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > In-Place Upgrade の実行を開始する前に保留中のシステム再起動が既に必要な場合、In-Place Upgrade はインストールの最後に再起動を求めしません。 これにより、Start-CSPool コマンドレットを使用してサービスを開始しようとするときに、最初のフロントエンド サーバーに対してアセンブリ例外がStart-CSPoolされます。 これらのエラーを解決するには、プール内のすべてのサーバーを再起動し、コマンドレットを再度実行します。 
  
- フロントエンド プール 以外のサーバーで、次のコマンドを使用してサービスを再起動します。
    
  ```powershell
  Start-CsWindowsService
  ```

[アップグレード] ページで **[OK]** In-Placeクリックすると、この手順を完了するために次のリマインダーが表示されます。
  
![一時アップグレードが正常に完了した後の次の手順を示すスクリーン ショット。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>手順 7: Skype for Business の機能が機能することを確認する

アップグレードが成功した場合は、アップグレードされたプールで Skype for Business をテストし、機能が期待通り動作しているのを確認します。 
  
### <a name="step-8-upgrade-secondary-pools"></a>手順 8: セカンダリ プールをアップグレードする

環境内に追加のプールがある場合は、このトピックの手順を繰り返してアップグレードします。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>アップグレードに関する問題In-Placeトラブルシューティングを行う

アップグレードがIn-Place、次の図のようなメッセージが表示されることがあります。 
  
![必要な累積的な更新プログラムがインストールされていない場合の一時アップグレードの失敗を示すスクリーン ショット。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
ページの下部にある完全なメッセージを確認して、問題のトラブルシューティングに役立ちます。 [ログ **の表示] をクリック** して詳細を表示します。
  
アップグレードの準備の確認または不足している前提条件のインストールで In-Placeアップグレードが失敗した場合は、サーバーに最新の Windows Server、Lync Server、および SQL Server の更新プログラムが適用され、必要なすべてのソフトウェアと役割がインストールされていることを確認します。 必要な機能の一覧については[、「Skype for Business Server 2015 のサーバー要件」および「Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)の前提条件のインストール」を参照してください。 [](install/install-prerequisites.md)
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 へのアップグレードを計画する](../plan-your-deployment/upgrade.md)
  
[Skype for Business Server 2015 のサーバー要件](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の前提条件のインストール](install/install-prerequisites.md)
  
[Skype for Business Server 2015 のインストール](install/install.md)
