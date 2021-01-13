---
title: Skype for Business Server のアーカイブ データベース オプションを変更する
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
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '概要: Skype for Business Server のアーカイブ データベース オプションを変更する方法について説明します。'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817697"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Skype for Business Server のアーカイブ データベース オプションを変更する

**概要:** Skype for Business Server のアーカイブ データベース オプションを変更する方法について説明します。
  
ユーザーのアーカイブ ストレージ用に SQL Server ストレージを使用してアーカイブを展開する場合は、次のデータベース ストレージを変更できます。
  
- アーカイブ ストレージに別SQL Serverデータベースを使用します。 これには、プライマリ アーカイブ データベースと、ミラーリングのミラーリングに使用SQL Serverがあります。
    
- Microsoft Exchange 統合に切り替えて、アーカイブ データとファイルを Exchange サーバーに保存します。 すべてのユーザーが Exchange サーバーに配置され、展開内のすべてのユーザーに Microsoft Exchange ストレージを使用する場合は、トポロジから SQL Server ストア データベースを削除する必要があります。 
    
これらの変更のいずれかを行う場合は、トポロジ ビルダーを実行し、変更を加え、トポロジを再度公開する必要があります。 Exchange サーバー **にSQL Server** Skype for Businessユーザーがいない場合は、アーカイブ ストアを指定したり、SQL Server ストアのミラーリング情報を有効にしたりしません。
  
## <a name="change-archiving-database-options"></a>アーカイブ データベース オプションの変更

1. Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルの Users グループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    > [!NOTE]
    > ローカル Users グループのメンバーであるアカウントを使用してトポロジを定義できますが、トポロジを公開するには、 トポロジにコンポーネントを追加するために必要なアカウントは **、Domain Admins** グループと **RTCUniversalServerAdmins** グループのメンバーであり、Skype for Business Server ファイル ストアで使用しているファイル共有に対するフル コントロールのアクセス許可 (読み取り、書き込み、変更) を持つアカウント (つまり、必要な随意アクセス制御リスト (DACL) または同等の権限を持つアカウントを構成できる) を使用する必要があります。
  
2. トポロジ ビルダーを開始します。
    
3. コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。
    
4. [**操作**] メニューの [**プロパティの編集**] をクリックします。 
    
5. [**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。
    
6. [**アーカイブ**] まで下方向にスクロールします。
    
7. [**アーカイブ**] で、次の操作を実行します。
    
   - 別の既存の SQL Server ストアに変更するには、[**アーカイブ SQL Server ストア**] ドロップダウン リスト ボックスで、次の操作を実行します。
    
   - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。
    
   - 新しい SQL Server ストアを定義するには、[**新規作成**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。
    
     - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。
    
     - 新しいストアをSQL Serverするには、[新規] をクリックし、[ストアの新しいSQL Server **定義**] ダイアログ ボックスで、次の操作を行います。
    
       - [SQL SERVER **FQDN]** で、新しいドメイン ストアを作成するサーバーの FQDN SQL Serverします。
    
       - 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
    
       - 指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。
    
   - ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングを有効にする**] を選択して、以下の作業をします。
    
     - 既存の SQL Server ストアをミラーリングに使用するには、[アーカイブ **SQL Server** ストアのミラー] ドロップダウン リスト ボックスで、ミラーリングに使用する SQL Server ストアの名前をクリックします。
    
     - ミラーリング用の新SQL Serverストアを指定するには、[新規] をクリックし、[新しい SQL Server **ストア** の定義] ダイアログ ボックスで、次のいずれかの操作を行います。
    
       a.  [SQL SERVER **FQDN]** で、新しいSQL Serverストアを作成する場所の FQDN をSQL Serverします。
    
       b. 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
    
       c. 指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。
    
   - SQL Server ミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリ SQL Server サーバーとミラー インスタンスの正常性を検出できる 3 つ目の独立した SQL Server インスタンス) を追加または変更する場合は **、[SQL Server** ミラーリング監視を使用して自動フェールオーバーを有効にする] チェック ボックスをオンにし、次のいずれかの操作を行います。
    
      a.  FQDN **SQL Server新** しいミラーリング監視を作成するサーバーの FQDN SQL Server指定します。
    
      b. 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。
    
      c. 指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。
    
   - Microsoft Exchange 統合に切り替えて、アーカイブ データとファイルを Exchange サーバーに保存するには (展開内のすべてのユーザーが Exchange サーバーに配置されている場合)、アーカイブ データベースのすべての情報を削除します。
    
     > [!IMPORTANT]
     > Exchange サーバーにホームではない Skype for Business ユーザーがいる場合は、ストア情報SQL Server削除しません。 
  
8. 構成を保存するには、[**OK**] をクリックします。
    
    > [!IMPORTANT]
    > トポロジ ビルダーで行った変更は、新しいトポロジを公開するまで有効ではありません。 詳細については [、「Skype for Business Server の既存の展開にアーカイブ データベースを追加する」を参照してください](../../deploy/deploy-archiving/add-archiving-databases.md)。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>アーカイブ データベースを使用してアーカイブ データベースの場所を変更Windows PowerShell

ほとんどの場合、アーカイブ サーバーのインストール時に指定されているアーカイブ データベースの場所を変更する必要は生じしません。 ただし、ハードウェア障害などの問題が発生した場合は **、Set-CsArchivingServer** コマンドレットを使用して、アーカイブ サーバーの接続を新しいデータベースに設定できます。
  
次の例では、ArchivingServer:atl-cs-001.contoso.com Archiving Server のアーカイブ データベースの場所を変更します。 この例では、新しいデータベースは ArchivingDatabase:atl-sql-001.contoso.com。
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


