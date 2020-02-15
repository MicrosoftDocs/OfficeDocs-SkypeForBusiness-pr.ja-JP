---
title: 'Lync Server 2013: 監視またはアーカイブデータの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8840869e972f0c178360b0b50644d352b8db85df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Lync Server 2013 での監視またはアーカイブデータの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-18_

障害が発生した後で Lync Server を起動して実行するには、監視およびアーカイブデータを復元する必要はありません。 ただし、組織にとってデータの監視とアーカイブが重要である場合は、データベースを再作成した後にデータを復元することをお勧めします。

次の手順では、SQL Server Management Studio を使用してアーカイブデータまたは監視データを復元する方法について説明します。

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>監視データまたはアーカイブ データをバックアップ ファイルから復元するには

1.  ローカルコンピューターの Administrators グループのメンバーとして、または同等のユーザー権限を持つグループのメンバーとして、復元するサーバーにログオンします。

2.  SQL Server Management Studio を開きます。 [**スタート**]、[**すべてのプログラム**]、[ **microsoft sql server 2012** ] または [ **microsoft sql server 2008 R2**] をクリックし、[ **sql server management Studio**] をクリックします。

3.  [**サーバーへの接続**] で、少なくともサーバーの名前と認証情報を入力して SQL Server インスタンスに接続します。

4.  [**オブジェクト エクスプローラー**] で、[**データベース**] を右クリックし、[**データベースの復元**] をクリックします。

5.  [**ページの選択**] で [**全般**] をクリックし、[**復元先データベース**] でデータベース名を次のように選択します。
    
      - アーカイブデータベースの場合は、[ **Lcslog**] を選択します。
    
      - 通話詳細記録 (CDR) データベースの場合は、[**LcsCDR**] を選択します。
    
      - Quality of Experience (QoE) データベースの場合は、[**QoEMetrics**] を選択します。

6.  [**復元元デバイス**] をクリックします。

7.  [**復元するバックアップ セットの選択**] で、バックアップ ファイルをクリックし、[**復元**] をクリックします。

8.  [**ページの選択**] で、[**オプション**] をクリックし、データ ファイルのパスとログのパスが適切なフォルダー内にあることを確認して、[**OK**] をクリックします。

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>アクセス制御リスト (Acl) が正しく設定されていることを確認するには

1.  [**データベース**] を展開し、アーカイブ データベースまたは監視データベース、[**セキュリティ**]、[**ユーザー**] の順に展開します。

2.  ドメイン グループ RTCComponentUniversalServices がユーザーとして存在することを確認します。

3.  RTCComponentUniversalServices が**ユーザー**の下に存在しない場合は、次の手順を実行します。
    
    1.  [ **ユーザー**] を右クリックし、[ **新しいユーザー**] をクリックします。
    
    2.  [**ログイン名**] に、不足しているグループ名 RTCComponentUniversalServices を入力します。
    
    3.  [**データベース ロールのメンバーシップ**] で、[**ServerRole**] アクセス許可を選択し、[**OK**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > アーカイブ サービスまたは監視サービスを再起動する必要はありません。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

