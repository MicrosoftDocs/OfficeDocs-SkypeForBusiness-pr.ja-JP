---
title: '[アーカイブ データベース のオプションを変更する] Skype for Business Server'
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
description: '概要: アーカイブ データベース のオプションを変更する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 74404b84be52a5a4b296029a61bd1060ebbc5f82a8aa1b3cdeb974cbfece6c44
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346473"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>[アーカイブ データベース のオプションを変更する] Skype for Business Server

**概要:** アーカイブ データベース のオプションを変更する方法については、Skype for Business Server。
  
ユーザーのアーカイブ ストレージSQL Serverを使用してアーカイブを展開する場合は、次のデータベース ストレージを変更できます。
  
- ストレージをアーカイブするためにSQL Server別のデータベースを使用します。 これには、プライマリ アーカイブ データベースと、ミラーリングに使用するデータベースSQL Server含まれます。
    
- Microsoft Exchangeに切り替えて、アーカイブ データとファイルをサーバーに保存Exchangeします。 すべてのユーザーが Exchange サーバーに配置され、展開内のすべてのユーザーに Microsoft Exchange ストレージを使用する場合は、トポロジから SQL Server ストア データベースを削除する必要があります。 
    
これらの変更のいずれかを行う場合は、トポロジ ビルダーを実行し、変更を加え、トポロジを再度発行する必要があります。 アーカイブ サーバー **にSQL Server** していない Skype for Business ユーザーを持たない限り、アーカイブ ストアまたは SQL Server ストア ミラーリング情報を有効にExchangeしません。
  
## <a name="change-archiving-database-options"></a>アーカイブ データベース オプションの変更

1. Skype for Business Server を実行しているコンピューター、または Skype for Business Server 管理ツールがインストールされているコンピューターで、ローカル Users グループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    > [!NOTE]
    > ローカルの Users グループのメンバーであるアカウントを使用してトポロジを定義できますが、トポロジを発行するには、 トポロジにコンポーネントを追加するために必要なアカウントは、Domain **Admins** グループと **RTCUniversalServerAdmins** グループのメンバーであり、Skype for Business Server ファイル ストアで使用するファイル共有に対する完全な制御アクセス許可 (読み取り、書き込み、変更) を持つアカウント (つまり、トポロジ ビルダーが必要な随意アクセス制御リスト (DACL) または同等の権限を持つアカウントを構成できる必要があります。
  
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
    
     - 新しいストアをSQL Serverするには、[新規] をクリックし、[新しいストア ストアの定義] SQL Serverで、次 **の** 操作を行います。
    
       - [SQL Server **FQDN]** で、新しいドメイン ストアを作成するサーバーの FQDN をSQL Serverします。
    
       - 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
    
       - 指定した SQL Server インスタンスがミラーリング関係にある場合は、[この **SQL** インスタンスがミラーリング関係にある] チェック ボックスをオンにし、[ミラー ポート番号] でポート番号を指定します。
    
   - ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングを有効にする**] を選択して、以下の作業をします。
    
     - ミラーリングに既存の SQL Server ストアを使用するには、[アーカイブ **SQL Server** ストア のミラー] ドロップダウン リスト ボックスで、ミラーリングに使用する SQL Server ストアの名前をクリックします。
    
     - ミラーリング用の新SQL Serverを指定するには、[新規] をクリックし、[新しいストア ストアの定義] SQL Server **で**、次のいずれかの操作を行います。
    
       a. [SQL Server **FQDN]** で、新しいドメイン ストアをSQL Serverするドメイン サーバーの FQDN をSQL Serverします。
    
       b. 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
    
       c. 指定した SQL Server インスタンスがミラーリング関係にある場合は、[この **SQL** インスタンスがミラーリング関係にある] チェック ボックスをオンにし、[ミラー ポート番号] でポート番号を指定します。
    
   - SQL Server ミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリ SQL Server サーバーとミラー インスタンスの正常性を検出できる 3 番目の独立した SQL Server インスタンス) を追加または変更する場合は、[SQL Serverミラーリング監視を使用して自動フェールオーバーを有効にする] チェック ボックスをオンにして、次のいずれかの操作を行います。
    
      a. [SQL Server **FQDN]** で、ミラーリング監視の新しいサーバーを作成するサーバーの FQDN をSQL Serverします。
    
      b. 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。
    
      c. 指定した SQL Server インスタンスがミラーリング関係にある場合は、[この **SQL** インスタンスがミラーリング関係にある] チェック ボックスをオンにし、[ミラー ポート番号] でポート番号を指定します。
    
   - microsoft Exchange 統合に切り替えて、アーカイブ データとファイルを Exchange サーバーに保存するには (展開内のすべてのユーザーが Exchange サーバーに配置されている場合)、アーカイブ データベースのすべての情報を削除します。
    
     > [!IMPORTANT]
     > サーバー上にSkype for BusinessユーザーがExchange場合は、そのユーザーストアSQL Server削除しません。 
  
8. 構成を保存するには、[**OK**] をクリックします。
    
    > [!IMPORTANT]
    > トポロジ ビルダーで行った変更は、新しいトポロジを公開するまで有効ではありません。 詳細については、「アーカイブ[データベースを既存の展開に追加する](../../deploy/deploy-archiving/add-archiving-databases.md)」を参照Skype for Business Server。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>アーカイブ データベースを使用してアーカイブ データベースの場所を変更Windows PowerShell

ほとんどの場合、アーカイブ サーバーのインストール時に指定されたアーカイブ データベースの場所を変更する必要が生じしません。 ただし、ハードウェア障害などの問題が発生した場合は **、Set-CsArchivingServer** コマンドレットを使用して、アーカイブ サーバーを新しいデータベースにポイントできます。
  
次の使用例は、アーカイブ サーバー:atl-cs-001.contoso.com の場所を変更します。 この例では、新しいデータベースは ArchivingDatabase:atl-sql-001.contoso.com。
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


