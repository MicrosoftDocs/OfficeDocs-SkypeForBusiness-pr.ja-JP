---
title: アーカイブおよび監視サーバーの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 従来の環境にアーカイブ サーバーと監視サーバーを展開した場合は、フロントエンド プールを移行した後、Skype for Business Server 2019 環境にこれらのサーバーを展開できます。 ただし、組織にとってアーカイブ機能と監視機能が重要な場合は、移行前にアーカイブと監視を Skype for Business Server 2019 パイロット プールに追加して、移行プロセス中に機能を利用できる必要があります。
ms.openlocfilehash: b1f497019d2043a7ea43c1134af615ae4db6183cd3d16593bfab6e835fa4db32
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303551"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>アーカイブおよび監視サーバーの移行

従来の環境にアーカイブ サーバーと監視サーバーを展開した場合は、フロントエンド プールを移行した後、Skype for Business Server 2019 環境にこれらのサーバーを展開できます。 ただし、組織にとってアーカイブ機能と監視機能が重要な場合は、移行前にアーカイブと監視を Skype for Business Server 2019 パイロット プールに追加して、移行プロセス中に機能を利用できる必要があります。 
  
移行プロセスで、アーカイブ機能と監視機能が必要な場合は、以下の点を考慮してください。
  
- アーカイブ データと監視データは、2019 年Skype for Business Serverに移動されません。 従来の環境を使用停止する前にバックアップしたデータは、従来の環境でのアクティビティの履歴になります。
    
- 従来のバージョンのアーカイブ サーバーと監視サーバーは、従来のフロントエンド プールにのみ関連付けできます。 2019 Skype for Business Serverでは、アーカイブと監視はサーバーの役割ではなく、Skype for Business Server 2019 フロントエンド プールに統合されています。
    
- Skype for Business Server 2019 年の従来の展開と 2019 年の展開が共存している間、従来のバージョンのアーカイブ サーバーと監視サーバーは、レガシ プールに保存されているユーザーのデータを収集します。 2019 年 2019 年のアーカイブと監視は Skype for Business Server、2019 年のプールにSkype for Business Server収集します。
    
    > [!NOTE]
    > 移行のフェーズで、新しい Skype for Business Server 2019 パイロット プールでレガシ エッジ サーバーを使用している場合、従来のバージョンのアーカイブ サーバーは、Skype for Business Server 2019 の従来のプールとアーカイブに存在するユーザーのデータを収集し続け、Skype for Business Server 2019 プールに存在するユーザーのデータを収集します。 
  
- Skype for Business Server 2019 のアーカイブと監視と共にサード パーティのアーカイブと監視ソリューションを使用する場合は、サードパーティ ソリューションを Skype for Business Server 2019 と統合する必要がある場合、ベンダーに相談してください。
    

