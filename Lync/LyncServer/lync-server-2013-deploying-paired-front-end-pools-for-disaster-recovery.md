---
title: 'Lync Server 2013: 障害復旧用のペアのフロントエンドプールの展開'
description: 'Lync Server 2013: 障害復旧用のペアのフロントエンドプールの展開。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4846121f301d2bc7be1af9b58f0a0fef3f88e6d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555903"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での障害復旧用のペアのフロントエンドプールの展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

トポロジビルダーを使用して、ペアになったフロントエンドプールの障害復旧トポロジを簡単に展開できます。

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>ペアのフロントエンド プールを展開するには

1.  プールが新規でまだ定義されていない場合は、トポロジビルダーを使用してプールを作成します。

2.  トポロジビルダーで、2つのプールのいずれかを右クリックし、[ **プロパティの編集**] をクリックします。

3.  左ウィンドウの [**復元**] をクリックし、右ウィンドウの [**関連付けられているバックアップ プール**] を選択します。

4.  [**関連付けられているバックアップ プール**] の下のボックスで、このプールとペアにするプールを選択します。別のプールとペアでない既存のプールのみ選択できます。
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  [**音声の自動フェールオーバーとフェールバック**] を選択し、[**OK**] をクリックします。
    
    このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの [**復元**] の下に表示されます。

6.  トポロジビルダーを使用してトポロジを公開します。

7.  2 つのプールがまだ展開されていない場合は、これらを展開すると、構成が完了します。最後の 2 つの手順を省略できます。
    
    しかし、ペアの関係を定義する前にプールが既に展開されていた場合は、次の 2 つの最終手順を実行する必要があります。

8.  両方のプール内のすべてのフロントエンド サーバーで、次のコマンドを実行します。
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    これによって、バックアップ ペアが適切に動作するために必要な他のサービスが構成されます。

9.  Lync Server 管理シェルコマンドプロンプトで、次のコマンドを実行します。
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. 次のコマンドレットを実行して、両方のプールのユーザーおよび電話会議データが相互に同期されるようにします。
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    データの同期には時間がかかる場合があります。 次のコマンドレットを使用して、状態を確認できます。 双方向の状態が安定していることを確認します。
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> [ <STRONG>音声の自動フェールオーバーとフェールバック</STRONG> ] オプションおよびトポロジビルダーの関連付けられた時間間隔は、Lync Server 2010 で導入された音声復元機能にのみ適用されます。 このオプションを選択しても、このドキュメントに記載されているプール フェールオーバーが自動的に行われるわけではありません。 プールのフェールオーバーとフェールバックを行うには、フェールオーバーとフェールバックのコマンドレットを、常に管理者が手動でそれぞれ起動する必要があります。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

