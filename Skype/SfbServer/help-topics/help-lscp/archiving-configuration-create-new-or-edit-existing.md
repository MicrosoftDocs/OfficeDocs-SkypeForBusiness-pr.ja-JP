---
title: アーカイブ構成の新規作成または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: アーカイブ構成を使用して、展開のアーカイブ オプションを制御します。 アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト構成およびプール構成が含まれます。
ms.openlocfilehash: e0f56e125919bcb27cd9523213c92b7906e89ff0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827017"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>アーカイブ構成: 新規作成または現在の形式のままで編集
 
アーカイブ構成を使用して、展開のアーカイブ オプションを制御します。 アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト構成およびプール構成が含まれます。
  
- **グローバル構成** グローバル構成は既定で作成されます。 グローバル構成を編集することはできますが、削除することはできません。 削除しようとすると、すべてのオプションが既定値にリセットされます。
    
- **サイトの構成 (オプション)** 特定のサイトのアーカイブ オプションを制御するために構成できる、1 つ以上のサイト アーカイブ構成を指定できます。 サイト構成はグローバル構成より優先されますが、アーカイブ サイト構成で指定されたサイトに対してだけ優先されます。 サイト構成を編集または削除できます。
    
- **プールの構成 (オプション)** 1 つ以上のプール アーカイブ構成を指定して、特定のプールのアーカイブ オプションを制御できます。 プール構成はグローバル構成とサイト構成より優先されますが、アーカイブ プール構成で指定されたプールに対してだけ優先されます。 プール構成を編集または削除できます。
    
> [!NOTE]
> アーカイブ構成は、Skype for Business Server にホームのユーザーに適用され、Microsoft Exchange 統合オプションを有効にして Exchange 2013 を使用してアーカイブ データを Microsoft Exchange に保存する場合は、Exchange 2013 にホームのユーザーに適用されます。 ただし、一部のオプションは、次のセクションで説明するように、Exchange 2013 にホームを持つユーザーに対して少し異なる方法で実装されます。 
  
新規または既存のアーカイブ構成の設定を構成するには、次のオプションを指定します。
- **名前** 各アーカイブ構成には名前が必要です。 名前は、追加または編集する構成の種類によって決まります。
    
  - **グローバル構成** 既定の名前は Global です。 例: "Contoso 北米組織"。
    
  - **サイトの構成** 一覧には、展開で使用可能なサイトが含まれている。 1 つのサイトをクリックして選択します。 例: "レドモンド データ センター"。
    
  - **プールの構成** 適切な名前を指定します。この名前には、展開内の特定のフロントエンド プールまたは Standard Edition サーバーの名前を指定できます。 たとえば、「マーケティング部門」とします。
    
- **説明** これはオプションです。 構成の範囲や使用など、追加の詳細を提供するために使用します。 たとえば、他のサイトの法務部門と調整します。
    
- **アーカイブ設定** 次のオプションがあります。
    
  - [**IM セッションをアーカイブする**]
    
  - [**IM および Web 会議セッションをアーカイブする**]
    
  - [**アーカイブを無効にする**]
    
- **アーカイブに失敗した場合のインスタント メッセージング (IM)** セッションまたは Web 会議セッションのブロックエラーは次のとおりです。
    
  - **IM** A failure could be a full database or problem with the storage service. この場合、アーカイブが有効になっているユーザーでは IM がブロックされます。
    
  - **会議** ファイル共有が使用できないか、記憶域サービスに問題がある可能性があります。 この場合、障害発生時にプールにホストされているすべてのアクティブな会議が制限モードに切り替えられ、新しい会議をアクティブ化できません。
    
    障害から回復した後、IM および会議は自動的に回復します。
    
- **Microsoft Exchange 統合** Exchange 2013 にホームを持つユーザーが含まれる場合は、このオプションを選択します。 このオプションでは、Exchange 2013 を使用して、ユーザーのメールボックスが保留リストに配置されている場合に、それらのユーザーのデータIn-Placeされます。 すべてのユーザーが Exchange 2013 にホームである場合は、アーカイブ データを保存するために個別の SQL Server データベースをセットアップする必要があります。
    
- **アーカイブ データの削除を有効にする** 削除を有効にするには、このオプションを選択し、次のような削除オプションを指定します。
    
  - 指定した特定の日数の後で削除する。
    
  - アーカイブ データがエクスポートされた後の削除 (Microsoft Exchange 統合を有効にした場合、Exchange にアップロードされたデータが含まれます)。
    
    > [!NOTE]
    > Microsoft Exchange 統合を有効にした場合、Exchange 2013 にホームとして、およびメールボックスが In-Place Hold に配置されているユーザーの削除は、Exchange によって制御されます。 唯一の例外は、Lync Server ファイル共有に格納されている会議ファイルです。 これらのファイルは、アーカイブ データがエクスポートされた後でデータを削除するオプションを選択した場合はファイルがエクスポートされた後 (Exchange にアップロードされた後)、保持する最大日数を指定した場合は指定した最大日数経過後にのみファイル共有から削除されます。 
  
Exchange 統合を含むアーカイブ機能の詳細については [、「Plan for archiving in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md) [Deploy archiving for Skype for Business Server 2015,](../../deploy/deploy-archiving/deploy-archiving.md)and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md)」を参照してください。

