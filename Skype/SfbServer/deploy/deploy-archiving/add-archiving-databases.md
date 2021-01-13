---
title: Skype for Business Server の既存の展開にアーカイブ データベースを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '概要: このトピックでは、Skype for Business Server 展開にアーカイブ データベースを追加する方法について説明します。'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820677"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Skype for Business Server の既存の展開にアーカイブ データベースを追加する
 
**概要:** このトピックでは、Skype for Business Server 展開にアーカイブ データベースを追加する方法について説明します。
  
アーカイブをサポートする展開を構成する前に、アーカイブをトポロジに組み込む必要があります。 このトピックでは、トポロジ ビルダーを使用して次の方法を実行する方法について説明します。
  
- アーカイブ データベースをトポロジに追加します。
    
- 更新されたトポロジを公開して、アーカイブ データベースを Skype for Business Server 展開に追加します。
    
> [!NOTE]
> Microsoft Exchange 統合を使用して、展開内のすべてのユーザーのアーカイブ データとファイルを Exchange サーバーに保存する場合は、アーカイブ **SQL Server** ストアまたは **SQL Server ストア** のミラーリング情報を使用するを指定しません。
  
### <a name="add-an-archiving-database-to-your-topology"></a>アーカイブ データベースをトポロジに追加する

1. Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルの Users グループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
2. トポロジ ビルダーを開始します。
    
3. コンソール ツリーで、アーカイブを展開するフロントエンド プールに移動し、アーカイブを展開するフロントエンド プールの名前をクリックします。
    
4. [**操作**] メニューの [**プロパティの編集**] をクリックします。 
    
5. [**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。
    
6. [**アーカイブ**] まで下方向にスクロールします。
    
7. [アーカイブ **] チェック ボックスを** オンにします。
    
8. [ **アーカイブ SQL Server] で、次** のいずれかの操作を行います。
    
   - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。 すべてのユーザーが Microsoft Exchange Server 2013 以上にホームを設定している場合は、Exchange のすべてのユーザーの Skype for Business 通信をアーカイブできます。 この場合、アーカイブ ストアを構成するSQL Server必要があります。
    
   - 新しいストアをSQL Serverするには、[新規] をクリックし、[ストアの新しいSQL Server **定義**] ダイアログ ボックスで、次の操作を行います。
    
   - [SQL SERVER **FQDN]** で、新しいドメイン ストアを作成するサーバーの FQDN SQL Serverします。
    
   - 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
    
   - 指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。
    
9. ストア ミラーリングを使用する場合SQL Serverストア ミラーリングを有効SQL Server **し**、次の操作を行います。
    
   - 既存の SQL Server ストアをミラーリングに使用するには、[アーカイブ **SQL Server** ストアのミラー] ドロップダウン リスト ボックスで、ミラーリングに使用する SQL Server ストアの名前をクリックします。
    
   - ミラーリング用の新しい SQL Server ストアを指定するには、[新規] をクリックし、[新しい SQL Server **ストア** の定義] ダイアログ ボックスで、次のいずれかの操作を行います。
    
     a.  [SQL SERVER **FQDN]** で、新しいSQL Serverストアを作成する場所の FQDN をSQL Serverします。
    
     b. 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
    
     c. 指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。
    
   - SQL Server ミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリ SQL Server とミラー インスタンスの正常性を検出できる 3 番目の独立した SQL Server インスタンス) を含める場合は **、[SQL Server** ミラーリング監視を使用して自動フェールオーバーを有効にする] チェック ボックスをオンにし、次のいずれかの操作を行います。
    
     a.  FQDN **SQL Server新** しいミラーリング監視を作成するサーバーの FQDN SQL Server指定します。
    
     b. 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。
    
     c. 指定した SQL Server インスタンスがミラーリング関係にある場合は、[This SQL **instance is in mirroring relation]** チェック ボックスをオンにし **、[Mirror port number]** でポート番号を指定します。
    
10. 構成を保存するには、[**OK**] をクリックします。
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>更新されたトポロジを公開してアーカイブ データベースを展開に追加する

1. Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカルの Users グループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    > [!NOTE]
    > ローカル Users グループのメンバーであるアカウントを使用してトポロジを定義できます。 ただし、トポロジにサーバーを追加するために必要なトポロジを公開するには **、Domain Admins** グループと **RTCUniversalServerAdmins** グループのメンバーであり、Skype for Business Server ファイル ストアで使用しているファイル共有に対するフル コントロールのアクセス許可 (読み取り、書き込み、および変更) を持つアカウント (必要な随意アクセス制御リスト (DACL) または同等の権限を持つアカウント) を使用する必要があります。
  
2. トポロジ ビルダーを使用して、前のセクションで作成したトポロジを開きます。
    
3. コンソール ツリーで **、Skype for Business Server** を右クリックし、[トポロジの公開] **をクリックします**。
    
4. [**トポロジの公開**] ページで、[**次へ**] をクリックします。
    
5. [**データベースの作成**] ページで、データベースが選択されていることを確認して、[**次へ**] をクリックします。 
    
    > [!NOTE]
    > データベースを作成するための適切なアクセス許可を持っていない場合、ここでのデータベースの選択を取り消して、適切なアクセス許可を持つ別のユーザーがデータベースを作成できます。 > 専用サーバー上のデータベースSQLトポロジ ビルダーを使用してインストールできます。 他のサーバー コンポーネントと併置されている SQL サーバー上のデータベースは、そのコンピューターでローカル セットアップを実行してインストールする必要があります。 
  
6. **[公開完了のウィザード]** ページで、トポロジが正常に公開されたことを確認し、**[完了]** をクリックします。
    
    > [!IMPORTANT]
    > トポロジを公開した後、コンテンツをアーカイブする前に、アーカイブのオプションおよびポリシーを構成する必要があります。 詳細については [、「Skype for Business Server のアーカイブ](configure-archiving-options.md) オプションを構成する」および「Skype for Business Server のアーカイブ ポリシー [を構成する」を参照してください](configure-archiving-policies.md)。 
  

