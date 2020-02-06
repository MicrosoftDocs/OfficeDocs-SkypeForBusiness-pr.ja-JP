---
title: Skype for Business Server 2015 へのアップグレード
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について説明します。 Skype for Business Server 2015 の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: c024cde12ce30f3d143bf5f3e34400cc49cb46b5
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791555"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Upgrade to Skype for Business Server 2015
 
**概要:** Lync Server 2013 から Skype for Business Server 2015 にアップグレードする方法について説明します。 [Microsoft 評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から Skype For business Server 2015 の無料トライアルをダウンロードします。
  
このドキュメントの手順を使用して、Skype for Business Server のトポロジビルダーと新しいインプレースアップグレード機能を使用して、Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。 Lync Server 2010 または Office Communications Server 2007 R2 からアップグレードする場合は、「 [Skype For Business Server 2015 へのアップグレードを計画](../plan-your-deployment/upgrade.md)する」を参照してください。

> [!NOTE]
> インプレースアップグレードは、Skype for Business Server 2015 で使用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。 サイドバイサイドの coexistance はサポートされています。詳細については、「 [Skype For Business Server 2019 への移行](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)」を参照してください。
  
## <a name="upgrade-from-lync-server-2013"></a>Lync Server 2013 からのアップグレード

Lync Server 2013 を Skype for Business Server 2015 にアップグレードするには、必須ソフトウェアのインストール、Skype for Business Server Topology Builder を使用した、プール内のデータベースのアップグレード、および Skype for Business Server のインプレースアップグレードの使用プールに関連付けられているサーバー。 アップグレードを完了するには、このトピックの 8 つの手順に従います。
  
### <a name="before-you-begin"></a>始める前に

- 「[Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md)」を確認します。
    
- [Skype For Business server 2015 のサーバー要件を](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)確認します。
    
- [Skype For Business Server 2015 の前提条件をインストール](install/install-prerequisites.md)します。
    
- [Skype For Business Server 2015 をインストール](install/install.md)します。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>手順 1: 管理ツールをインストールしてトポロジをダウンロードする

1. Lync OCSCore またはその他の Lync コンポーネントがインストールされていないトポロジのコンピューターに接続します。
    
2. Skype for Business Server 2015 インストールメディアから、 **OCS_Volume \setup\amd64**から**setup.exe**を実行します。 
    
3. [**インストール**] をクリックします。 
    
4. ライセンス契約に同意します。
    
5. 展開ウィザードで、[**管理ツールのインストール**] をクリックして、インストールの手順に従います。
    
     ![[管理ツールのインストール] へのリンクが強調された展開ウィザードのスクリーン ショット](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Windows のスタート画面で、Skype for Business Server トポロジビルダーを開きます。
    
7. [**既存の展開からトポロジをダウンロードする**] をクリックして、[**次へ**] をクリックします。
    
8. トポロジの名前を入力して、[**保存**] をクリックします。
    
9. トポロジを保存した場所に移動して、トポロジのコピーを作成します。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>手順 2: トポロジ ビルダーを使用して、トポロジをアップグレードして公開する

アップグレードを開始する前に、アップグレードを計画しているプールのすべてのサービスが実行されている必要があります。 これは、トポロジの変更が、プール内のサーバーのローカル データベースにレプリケートされるようにするためです。
  
> [!IMPORTANT]
>  アップグレードの前に、トポロジ ファイルのコピーを保存します。 アップグレードした後は、トポロジをダウングレードすることはできません。 > 永続的なチャットサービスが、常設チャットデータベースと同じサーバー上にある場合は、この手順をスキップして、手順4に進みます。 サービスを停止した後、各サーバー上で一括アップグレードのセットアップを実行して、ローカル データベースをアップグレードします。
  
> [!NOTE]
> ミラー化されているバック エンド データベースがトポロジに含まれる場合、トポロジ ビルダーを使用して**トポロジを公開すると**、プリンシパル データベースとミラー化されたデータベースの両方が表示されます。トポロジを公開するときは、すべてのデータベースがプリンシパル上で実行されていて、ミラーではなくプリンシパルのみを選択していることを確認してください。条件が満たされていない場合、トポロジを公開した後に警告が表示されます。
  
以下のいずれかのオプションを選び、Skype for Business Server 2015 Topology Builder を使用して、新しいトポロジをアップグレードして公開します。 手順を完了し、アップグレードしたトポロジを公開した後、このトピックの手順 3 に進みます。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>オプション 1: 孤立したフロントエンド プールと、関連するアーカイブ ストアと監視ストアをアップグレードする

アップグレードするプールにアーカイブ ストアと監視ストアの依存関係が存在する場合、以下の手順に従って、アーカイブ ストアと監視ストアもアップグレードされます。
  
1. [トポロジビルダー] で、Lync Server 2013 プールを右クリックし、[ **Skype For Business Server 2015 にアップグレード**] を選択して、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションが含まれる右クリック メニューのスクリーン ショット](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. トポロジビルダーで、[**アクション** > **発行トポロジ**] または [**アクション** > **トポロジ** > の**公開**] をクリックします。 
    
     ![トポロジ ビルダーの [アクション] メニューの [トポロジの公開] オプションのスクリーン ショット](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 公開時に、アーカイブ ストアと監視ストアへのデータベースのインストールを選択します。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>オプション 2: アーカイブおよび監視ストアをアップグレードせずに、フロントエンドプールをアップグレードする

以下の手順に従うと、選択したプールのアーカイブと監視が無効になります。アップグレード後、プールにはアーカイブ ストアと監視ストアは存在しなくなります。
  
1. [トポロジビルダー] で、アップグレードする Lync Server 2013 プールを選択します。
    
2. Lync Server 2013 アーカイブおよび監視ストアへの依存関係を削除します。 
    
   - [**アクション** > の**編集プロパティ**] に移動します。
    
   - [**アーカイブ**] チェック ボックスをオフにします。
    
     ![[プロパティの編集] ダイアログの [アーカイブ] チェックボックスのスクリーン ショット](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - [**監視**] チェック ボックスをオフにします。
    
     ![[監視] チェックボックスを示している、[プロパティの編集] ダイアログのスクリーン ショット](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 プールを右クリックし、[ **Skype For Business Server 2015 にアップグレード**] を選択して、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションが含まれる右クリック メニューのスクリーン ショット](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. トポロジビルダーで、[**アクション** > **発行トポロジ**] または [**アクション** > **トポロジ** > の**公開**] をクリックします。 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>オプション 3: フロントエンドプールをアップグレードし、それに関連付けた新しい Skype for Business Server 2015 アーカイブと監視ストア

以下の手順に従うと、アーカイブと監視が以前のストアで停止され、作成した新しいストアで開始されます。 
  
1. [トポロジビルダー] で、アップグレードする Lync Server 2013 プールを選択します。 
    
2. Lync Server 2013 アーカイブおよび監視ストアへの依存関係を削除します。 
    
   - [**アクション** > の**編集プロパティ**] に移動します。
    
   - [**アーカイブ**] チェック ボックスをオフにします。
    
     ![[プロパティの編集] ダイアログの [アーカイブ] チェックボックスのスクリーン ショット](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - [**監視**] チェック ボックスをオフにします。
    
     ![[監視] チェックボックスを示している、[プロパティの編集] ダイアログのスクリーン ショット](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 プールを右クリックし、[ **Skype For Business Server 2015 にアップグレード**] を選択して、手順に従います。 
    
     ![Lync Server 2013 のアップグレード オプションが含まれる右クリック メニューのスクリーン ショット](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. アーカイブ用の新しい SQL ストアを作成します。 
    
   - プールと**アクション** > の**編集プロパティ**を選びます。 
    
   -  [**アーカイブ**] チェック ボックスをオンにします。
    
   - [**新規**] をクリックします。
    
     ![[アーカイブ] セクションの [新規] ボタンを示している、[プロパティの編集] ダイアログのスクリーン ショット](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 監視用の新しい SQL ストアを作成します。 
    
   - プールと**アクション** > の**編集プロパティ**を選びます。 
    
   -  [**監視**] チェック ボックスをオンにします。
    
   - [**新規**] をクリックします。
    
     ![[監視] セクションの [新規] ボタンを示している、[プロパティの編集] ダイアログのスクリーン ショット](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. トポロジビルダーで、[**アクション** > **発行トポロジ**] または [**アクション** > **トポロジ** > の**公開**] をクリックします。 
    
7. 公開時に、新しいアーカイブ ストアと監視ストアへのデータベースのインストールを選択します。
    
### <a name="step-3-wait-for-replication"></a>手順 3: レプリケーションを待機する

更新されたトポロジを、環境内のすべてのサーバーに公開するために、レプリケーションが完了するまで少し待ちます。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>手順 4: アップグレードするプールですべてのサービスを停止する

アップグレードするプールをサービスしている各サーバーで、PowerShell で次のコマンドレットを実行します。
  
```powershell
Disable-CsComputer -Scorch
```

インプレースアップグレード処理中にサーバーの再起動が必要になる場合があるため、[無効-CsComputer] を使うことをお勧めします。 Stop-CsWindowsService を使った場合、再起動後に一部のサービスが自動的に再起動されることがあります。 これにより、インプレースアップグレードが失敗することがあります。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>手順 5: フロントエンド プールと非フロントエンド プール サーバーをアップグレードする

> [!NOTE]
>  アップグレード前に、Skype for Business Server 2015 に必要なすべての新しい前提条件をインストールしてください。アップグレードを試みる前に、32 GB 以上の空き領域を > してください。 また、ドライブが固定ローカルドライブであり、USB または Firewire で接続されていないことを確認してください。は、NTFS ファイルシステムで書式設定されていますが、圧縮されておらず、ページファイルも含まれていません。最新の Lync Server 2013 の累積的 > な更新プログラムがインストールされていることを > します。 > windows server 2008 r2-KB2533623> Windows server[](https://support.microsoft.com/kb/2533623) r2-KB2858668> Windows server[>](https://support.microsoft.com/kb/2858668) 2012 > 2012 r2-2012[KB2982006](https://support.microsoft.com/kb/2982006)
  
各サーバーでインプレースアップグレードを使用して、フロントエンドプール、エッジプール、仲介サーバー、常設チャットプールを更新します。
  
1. 各サーバーで、Skype for Business Server 2015 インストールメディアの**OCS_Volume \setup\amd64**から**setup.exe**を実行します。
    
2. 使用許諾契約に同意し、インプレースアップグレードのプロンプトに従います。
    
3. フロントエンドプールとフロントエンドプールサーバーの各サーバーについて、この手順を繰り返します。
    
> [!NOTE]
> インプレースアップグレード中にサーバーを再起動するように求められる場合があります。 いいですよ。 再起動後、インプレースアップグレードは中断した場所から続行されます。 
  
一括アップグレードが正常に完了すると、次のメッセージが表示されます。
  
![正常に完了した一括アップグレードのスクリーン ショット](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>手順 6: アップグレードしたすべてのサーバーでサービスを再開する

> [!NOTE]
> サービスを再起動する前に、%ProgramData%\WindowsFabric がすべてのフロントエンドサーバーに存在しないことを確認してください。 存在する場合は、サービスを開始する前に削除します。 
  
- フロントエンドプール内のすべてのサーバーのアップグレードが完了したら、次の PowerShell コマンドを使用してサービスを再起動します。 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > 一括アップグレードの実行開始前に再起動が必要な保留中のシステムが既に存在する場合は、インストールの最後に一括アップグレードから再起動は求められません。これにより、Start-CSPool コマンドレットを使用してサービスを開始しようとすると、最初のフロントエンド サーバーに対してアセンブリ例外がスローされます。このようなエラーを解決するには、プール内の全サーバーを再起動し、このコマンドレットをもう一度実行してください。 
  
- 非フロントエンド プール サーバーでは、以下のコマンドを実行してサービスを再開します。
    
  ```powershell
  Start-CsWindowsService
  ```

一括アップグレードのページで [**OK**] をクリックした後、この手順を完了するための以下の通知が表示されます。
  
![一括アップグレードが正常に完了した後の、次のステップを示しているスクリーン ショット](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>手順 7: Skype for Business 機能の動作を確認する

アップグレードが成功したことを確認するには、アップグレードされたプールについて、Skype for Business をテストして、機能が期待どおりに機能していることを確認します。 
  
### <a name="step-8-upgrade-secondary-pools"></a>手順 8: 二次的なプールをアップグレードする

このトピックの手順を繰り返して、環境に存在する他のプールをすべてアップグレードします。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>一括アップグレードの問題をトラブルシューティングする

一括アップグレードが失敗すると、次の図のようなメッセージが表示される場合があります。 
  
![必須の累積的な更新プログラムがインストールされていないために一括アップグレードが失敗していることを示しているスクリーン ショット](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
ページの下部にあるすべてのメッセージを確認して、問題のトラブルシューティングに役立てます。 詳細情報を表示するには、[**ログの表示**] をクリックします。
  
**アップグレードの準備状況の確認**でインプレースアップグレードが失敗した場合、または必要な**前提条件をインストール**していない場合は、サーバーに最新の Windows server、Lync server、SQL server の更新プログラムがすべてインストールされていることを確認してください。また、必要なソフトウェアとロールがすべてインストールされている必要があります 必要なものの一覧については、「Skype for business [server 2015 のサーバー要件](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」および「 [Skype for business server 2015 の前提条件をインストール](install/install-prerequisites.md)する」を参照してください。
  
## <a name="see-also"></a>関連項目

[Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の前提条件のインストール](install/install-prerequisites.md)
  
[Skype for Business Server 2015 のインストール](install/install.md)
