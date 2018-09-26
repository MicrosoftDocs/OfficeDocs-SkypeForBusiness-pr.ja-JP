---
title: フロント エンド プールまたは Standard Edition サーバーを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このトピックでは、フロント エンド プールまたはサーバーを標準的な版フロント エンド サーバーを削除するプロセスについて説明します。 フロント エンド プールを削除すると、各フロント エンド サーバー プールの削除処理の一部として、プールに属しているを削除します。 標準 Edition フロント エンド サーバーを削除すると、トポロジ ビルダーで SQL ストアの定義を削除する必要があります。
ms.openlocfilehash: 7e56f2e9ff57536d1f065452f299a9af33a46aee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028888"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>フロント エンド プールまたは Standard Edition サーバーを削除します。

この資料では、フロント エンド プールまたはサーバーを標準的な版フロント エンド サーバーを削除するプロセスについて説明します。 フロント エンド プールを削除すると、各フロント エンド サーバー プールの削除処理の一部として、プールに属しているを削除します。 標準 Edition フロント エンド サーバーを削除すると、トポロジ ビルダーで SQL ストアの定義を削除する必要があります。
  
## <a name="to-remove-a-front-end-server-pool"></a>フロント エンド サーバー プールを削除するには

1. トポロジ ビルダーを開きます。
    
2. 従来のノードに移動します。
    
3. **エンタープライズ エディションのフロント エンド プール**] を展開フロント エンド プールを展開しを削除するには、フロント エンド プールを右クリックし、し、[**削除**] をクリックします。
    
4. トポロジを公開、レプリケーション ・ ステータスを確認、必要に応じて、従来の展開ウィザードを実行します。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>標準のエディションのフロント エンド サーバーを削除するには

1. トポロジ ビルダーを開きます。
    
2. バージョンのインストール] ノードに移動します。
    
3. **標準のエディションのフロント エンド サーバー**を展開を削除するには、フロント エンド サーバーを右クリックし、[**削除**] をクリックします。
    
4. **SQL ストア**を展開し、標準のエディションのフロント エンド サーバーに関連付けられている SQL Server データベースを右クリックし、[**削除**] をクリックします。
    
    > [!IMPORTANT]
    > 標準のエディションのフロント エンド サーバーから配置されている SQL Server データベースの定義を削除する必要があります。 
  
5. トポロジを公開、レプリケーション ・ ステータスを確認し、必要に応じて、展開ウィザードを実行します。 
    

