---
title: Skype for Business Server でアーカイブデータベースのオプションを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '概要: Skype for Business Server のアーカイブデータベースオプションを変更する方法について説明します。'
ms.openlocfilehash: 3e7ae30e012464b6d1f72e323dd60ad397e7430d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992764"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Skype for Business Server でアーカイブデータベースのオプションを変更する

**概要:** Skype for Business Server のアーカイブデータベースのオプションを変更する方法について説明します。
  
いずれかのユーザーのために SQL Server ストレージを使用してアーカイブを展開している場合は、次のデータベース記憶域を変更することができます。
  
- アーカイブストレージとして別の SQL Server データベースを使用します。 これには、プライマリアーカイブデータベースと、SQL Server ミラーリングで使用するデータベースが含まれます。
    
- Exchange server にアーカイブデータとファイルを保存するには、Microsoft Exchange 統合に切り替えます。 すべてのユーザーが Exchange サーバーを使用していて、展開内のすべてのユーザーに対して Microsoft Exchange ストレージを使用する場合は、SQL Server ストアデータベースをトポロジから削除する必要があります。 
    
これらの変更を行うには、トポロジビルダーを実行し、変更を行ってから、トポロジをもう一度公開する必要があります。 Skype for Business ユーザーが Exchange サーバーを使っていない場合は、**アーカイブ Sql server ストア**または**sql server ストアのミラーリング**情報を有効にしないようにします。
  
## <a name="change-archiving-database-options"></a>アーカイブ データベース オプションの変更

1. Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    > [!NOTE]
    > トポロジを定義するには、[ローカルユーザー] グループのメンバーであるアカウントを使用します。ただし、トポロジを公開するには、トポロジにコンポーネントを追加するために必要なトポロジを指定します。 **Domain Admins**グループと**RTCUniversalServerAdmins**グループのメンバーであり、Skype for business Server ファイルストアで使用しているファイル共有に対してフルコントロールのアクセス許可 (つまり読み取り、書き込み、変更) を持つアカウントを使用する必要があります (つまり、トポロジビルダーが必要な随意アクセス制御を構成できるようにします)。リスト (Dacl)、または同等の権限を持つアカウント。
  
2. トポロジビルダーを起動します。
    
3. コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。
    
4. [**アクション**] メニューの [**プロパティの編集**] をクリックします。 
    
5. [**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。
    
6. [**アーカイブ**] まで下方向にスクロールします。
    
7. [**アーカイブ**] で、次の操作を実行します。
    
   - 別の既存の SQL Server ストアに変更するには、[**SQL Server ストアのアーカイブ**] ドロップダウン リスト ボックスで、次の操作を実行します。
    
   - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。
    
   - 新しい SQL Server ストアを定義するには、[**新規**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。
    
     - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。
    
     - 新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次の操作を行います。
    
       - [ **Sql SERVER fqdn**] で、新しい SQL Server ストアを作成するサーバーの fqdn を指定します。
    
       - 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
    
       - 指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
   - ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングの有効化**] を選択して、以下の操作を実行します。
    
     - ミラーリング用の既存の SQL Server ストアを使用するには、[**アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。
    
     - ミラーリング用の新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次のいずれかの操作を行います。
    
       a. [ **Sql SERVER fqdn**] で、新しい sql server ストアを作成する sql SERVER の fqdn を指定します。
    
       b. 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
    
       c. 指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
   - Sql server のミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリ SQL Server サーバーの正常性を検出できる別の SQL Server インスタンス) を追加または変更する場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効**にする] チェックボックスをオンにして、次のいずれかの操作を行います。
    
      a. [ **Sql SERVER fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。
    
      b. 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。
    
      c. 指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
   - Exchange server にアーカイブデータとファイルを保存するために Microsoft Exchange との統合を切り替えるには (展開内のすべてのユーザーが Exchange サーバーに所属している場合)、アーカイブデータベースのすべての情報を削除します。
    
     > [!IMPORTANT]
     > Exchange サーバーを使用していない Skype for Business ユーザーがいる場合は、SQL Server ストアの情報を削除しないでください。 
  
8. 構成を保存するには、[**OK**] をクリックします。
    
    > [!IMPORTANT]
    > トポロジビルダーで行った変更は、新しいトポロジを公開するまで有効になりません。 詳細については、「 [Skype For Business Server の既存の展開にアーカイブデータベースを追加する](../../deploy/deploy-archiving/add-archiving-databases.md)」を参照してください。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Windows PowerShell を使用したアーカイブ データベースの場所の変更

ほとんどの場合は、アーカイブ サーバーをインストールするときに指定されたアーカイブ データベースの場所を変更する必要はありません。 ただし、ハードウェア障害や他の問題が発生した場合は、**Set-CsArchivingServer** コマンドレットを使用して、アーカイブ サーバーが新しいデータベースを参照するように設定できます。
  
次の例では、ArchivingServer: atl-001.contoso.com アーカイブサーバーのアーカイブデータベースの場所を変更します。 この例では、新しいデータベースが ArchivingDatabase:atl-sql-001.contoso.com に置かれます。
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


