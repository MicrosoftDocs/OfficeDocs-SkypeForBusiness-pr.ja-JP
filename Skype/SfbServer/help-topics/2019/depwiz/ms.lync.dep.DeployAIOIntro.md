---
title: 単一の Standard Edition サーバーの準備 (開始)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 中央管理ストアとその他の配置されているサービスを選択することを保持するビジネス サーバー 2015 の Standard Edition サーバーは、Skype のインストールを開始するのにはサーバー上のローカルの Administrators グループのメンバーとしてログオンしなければなりませんStandard Edition サーバーになります。 1 つの標準エディションのサーバーの準備] ページでは、最初にインストールするための要件について説明します。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
ms.openlocfilehash: 32a8241e2a7259b8b59007f62d4d604cab94f16e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988818"
---
# <a name="prepare-single-standard-edition-server-intro"></a>単一の Standard Edition サーバーの準備 (開始)
 
中央管理ストアとその他の配置されているサービスを選択することを保持するビジネス サーバー 2015 の Standard Edition サーバーは、Skype のインストールを開始するのにはサーバー上のローカルの Administrators グループのメンバーとしてログオンしなければなりませんStandard Edition サーバーになります。 [**単一の Standard Edition サーバーの準備**] ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
  
この特別なタスクは、Standard Edition サーバーをインフラストラクチャの最初のサーバーとして設定するように設計されています。 このタスクでは、Standard Edition サーバー上に SQL Server Express は、中央管理ストアをインストールします。 別の Standard Edition サーバーまたはフロントエンド プールを既に展開している場合は、[**キャンセル**] をクリックします。
  
> [!NOTE]
> このタスクを完了するは、(を既にインストールしていない) 場合は、トポロジ ビルダーをインストールし、トポロジ ドキュメントを構成します。 このトピックで説明するタスクを完了すると展開される中央管理ストアが利用できるようになるまで、トポロジ ドキュメントを公開することはできません。 
  

