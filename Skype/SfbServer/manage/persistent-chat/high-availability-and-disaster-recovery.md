---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '概要: Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を管理する方法について学習します。'
ms.openlocfilehash: 7ec7182d8fe2866499f731b43df712a69c44bc42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815047"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の管理
 
**概要:** Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を管理する方法について学習します。
  
このトピックでは、常設チャット サーバーをフェールオーバーおよびフェールバックする方法について説明します。 このトピックを読む前に [、「Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) および [「Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)を参照してください。

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 
  
## <a name="fail-over-persistent-chat-server"></a>常設チャット サーバーのフェールオーバー

常設チャット サーバーのフェールオーバーは、主に手動プロセスとして設計されています。
  
フェールオーバー手順は、セカンダリ データ センターが稼働しているが、プライマリ常設チャット データベースがある常設チャット サーバー サービスは、次のような完全に使用できないという前提に基づいて行います。
  
- 常設チャット サーバープライマリ データベースと常設チャット サーバー ミラー データベースがダウンしています。
    
- Skype for Business Server フロントエンド サーバーがダウンしています。
    
操作は 2 つの基本手順に基づいて行われます。
  
- プライマリ 常設チャット データベース (mgc) を回復します。
    
- 新しいプライマリ データベースのミラーリングを確立する。
    
常設チャット コンプライアンス データベース (mgccomp) はフェールオーバーされません。 このデータベースの内容は一時的なものであり、コンプライアンス アダプターがデータを処理するときに削除されます。 データ損失を回避するためにアダプター出力を正しく管理する責任は、常設チャット管理者の責任です。
  
常設チャット サーバーをフェールオーバーするには:
  
1. 常設チャット サーバー バックアップ ログ配布データベースからログ配布を削除します。
    
   - このSQL Server Management Studio、常設チャット サーバー バックアップ mgc データベースがあるデータベース インスタンスに接続します。
    
   - マスター データベースに対するクエリ ウィンドウを開きます。
    
   - 次のコマンドを使用して、ログ配布を削除します。
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. バックアップ共有から、バックアップ サーバーのコピー先フォルダーへ、コピーしていないバックアップ ファイルをコピーします。
    
3. セカンダリ データベースに、適用していないトランザクション ログ バックアップを順番に適用します。 詳細については、「 [方法: トランザクション ログ バックアップを適用する (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428)を参照してください。
    
4. バックアップ mgc データベースをオンラインにします。手順 1b. で開いたクエリ ウィンドウを使用して、次の手順を実行します。
    
   - mgc データベースへのすべての接続を終了します (接続がある場合)。
    
   - **exec** sp_who2、mgc データベースへの接続を識別します。
    
   - **kill \<spid\>** を使用して、これらの接続を終了します。
    
   - データベースをオンラインにします。
    
   - **回復を使用してデータベース mgc を復元します**。
    
5. Skype for Business Server 管理シェルで **、Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** コマンドを使用して、mgc バックアップ データベースにフェールオーバーします。 常設チャット プールの完全修飾ドメイン名を、必ずこの名前に置き換atl-cs-001.litwareinc.com。
    
    mgc バックアップ データベースがプライマリ データベースとして動作するようになります。
    
6. Skype for Business Server 管理シェルで **、Install-CsMirrorDatabase** コマンドレットを使用して、プライマリ データベースとして機能するバックアップ データベースの高可用性ミラーを確立します。 バックアップ データベース インスタンスをプライマリ データベースとして使用し、バックアップ ミラー データベース インスタンスをミラー インスタンスとして使用します。 これは、セットアップ時にプライマリ データベースに対して最初に構成したミラーと同じものではありません。
    
7. 常設チャット サーバーのアクティブ なサーバーを設定します。 Skype for Business Server 管理シェルから **Set-CsPersistentChatActiveServer** コマンドレットを使用して、アクティブ なサーバーの一覧を設定します。
    
    > [!IMPORTANT]
    > すべてのアクティブ サーバーが新しいプライマリ データベースと同じデータ センター内に置かれているか、このデータベースへの接続が低待機時間/高帯域幅であるデータセンター内に置かれている必要があります。 
  
    この時点で、常設チャット サーバープライマリ データベースから常設チャット サーバー バックアップ データベースへのフェールオーバーは正常に完了します。
    
## <a name="fail-back-persistent-chat-server"></a>常設チャット サーバーのフェールバック

この手順では、常設チャット サーバーの障害から回復し、プライマリ データ センターから操作を再確立するために必要な手順の概要を示します。
  
常設チャット サーバーの障害が発生すると、プライマリ データ センターが完全に停止し、プライマリ データベースとミラー データベースが使用できなくなる。 プライマリ データ センターはバックアップ サーバーにフェールオーバーします。
  
以下の手順では、プライマリ データ センターがバックアップされ、サーバーが再構築された後、通常の動作を回復します。 この手順では、プライマリ データ センターが完全な停止から回復され、トポロジ ビルダーを使用して mgc データベースと mgccomp データベースが再構築および再インストールされたと想定しています。
  
また、この手順では、フェールオーバー期間中に新しいミラー サーバーとバックアップ サーバーが展開されていないと想定し、展開されたサーバーはバックアップ サーバーとそのミラー サーバーのみである必要があります。これは、前の「常設チャット サーバーのフェールオーバー」で定義されています。
  
この手順の意図は、プライマリ サーバーからバックアップ サーバーへのフェールオーバーの原因となった障害が発生する前の状態に構成を復旧することにあります。
  
1. Skype for Business Server 管理シェルから **Set-CsPersistentChatActiveServer** コマンドレットを使用して、常設チャット サーバーの Active Server リストからすべてのサーバーをクリアします。 これにより、フェールバック中に、すべての常設チャット サーバーが mgc データベースと mgccomp データベースに接続しなくるのを停止します。
    
    > [!IMPORTANT]
    > セカンダリSQL Server常設チャット サーバー のバック エンド サーバー上の管理者エージェントが特権アカウントで実行されている必要があります。 このアカウントには、次のアクセス許可が与えられている必要があります。 
  
   - バックアップが置かれるネットワーク共有に対する読み取りアクセス
    
   - バックアップのコピー先となるローカル ディレクトリに対する書き込みアクセス
    
2. バックアップ mgc データベースでのミラーリングを無効にします。
    
   - このSQL Server Management Studio、バックアップ mgc インスタンスに接続します。
    
   - mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**ミラー**] をクリックします。
    
   - [**ミラーリングの削除**] をクリックします。
    
   - [**OK**] をクリックします。
    
   - mgccomp データベースに対しても同じ手順を実行します。
    
3. mgc データベースをバックアップして、新しいプライマリ データベースに復元できるようにします。
    
   - バックアップ SQL Server Management Studio、バックアップ mgc インスタンスに接続します。
    
   - mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**バックアップ**] をクリックします。[**データベースのバックアップ**] ダイアログ ボックスが表示されます。
    
   - [**バックアップの種類**] で、[**完全**] を選択します。
    
   - [**バックアップ コンポーネント**] として、[**データベース**] をクリックします。
    
   - [**名前**] に表示される既定のバックアップ セット名をそのまま使用するか、バックアップ セット名として別の名前を入力します。
    
   -  *\<Optional\>*  [ **説明]** に、バックアップ セットの説明を入力します。
    
   - バックアップ先の一覧から既定のバックアップ場所を削除します。
    
   - ログ配布用に設定した共有の場所へのパスを使用して、この一覧にファイルを追加します。このパスはプライマリ データベースとバックアップ データベースの両方に使用できます。
    
   - [**OK**] をクリックします。ダイアログ ボックスが閉じられ、バックアップ プロセスが開始されます。
    
4. 上記のステップで作成されたバックアップ データベースを使用して、プライマリ データベースを復元します。
    
   - このSQL Server Management Studio、プライマリ mgc インスタンスに接続します。
    
   - mgc データベースを右クリックし、[**タスク**]、[**復元**] の順にポイントしてから、[**データベース**] をクリックします。[**データベースの復元**] ダイアログ ボックスが表示されます。
    
   - [**復元元デバイス**] を選択します。
    
   - [参照] ボタンをクリックします。[**バックアップの指定**] ダイアログ ボックスが表示されます。[**バックアップ メディア**] で、[**ファイル**] を選択します。[**追加**] をクリックし、ステップ 3. で作成したバックアップ ファイルを選択し、[**OK**] をクリックします。
    
   - [**復元するバックアップ セットの選択**] で、バックアップを選択します。
    
   - [**ページの選択**] ペインで、[**オプション**] をクリックします。
    
   - [**復元オプション**] で、[**既存のデータベースを上書きする**] を選択します。
    
   - [**復旧状態**] で、[**データベースを使用可能な状態にする**] を選択します。
    
   - [**OK**] をクリックします。復元プロセスが開始されます。
    
5. プライマリ SQL Serverログ配布を構成します。 [「Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)の手順に従って、プライマリ mgc データベースのログ配布を確立します。
    
6. 常設チャット サーバーのアクティブ なサーバーを設定します。 Skype for Business Server 管理シェルから **Set-CsPersistentChatActiveServer** コマンドレットを使用して、アクティブ なサーバーの一覧を設定します。
    
    > [!IMPORTANT]
    > すべてのアクティブ サーバーが新しいプライマリ データベースと同じデータ センター内に置かれているか、このデータベースへの接続が低待機時間/高帯域幅であるデータセンター内に置かれている必要があります。 
  
プールを通常の状態に復元するには、次のコマンドWindows PowerShellします。
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

詳細については [、Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
  

