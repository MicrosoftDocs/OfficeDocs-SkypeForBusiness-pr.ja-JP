---
title: トポロジの選択の CMS のページを公開します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーを使用して構成したトポロジを公開します。 フロント エンド サーバーまたはフロント エンド プールは、中央管理ストアを保持しているの役割を仮定したリストから選択するように求められます。 フロント エンド サーバーまたはフロント エンド プールを 1 つだけでは、任意の時点で、この役割を保持できます。
ms.openlocfilehash: 5f5c25982194246490232966d5c7da3a48759a57
ms.sourcegitcommit: 16421e244f866e13600765a41cca509202815819
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "22290281"
---
# <a name="publish-topology-select-cms-page"></a>トポロジの選択の CMS のページを公開します。
 
トポロジ ビルダーを使用して構成したトポロジを公開します。 フロント エンド サーバーまたはフロント エンド プールは、中央管理ストアを保持しているの役割を仮定したリストから選択するように求められます。 フロント エンド サーバーまたはフロント エンド プールを 1 つだけでは、任意の時点で、この役割を保持できます。 
  
### <a name="about-the-central-management-server"></a>サーバーの全体管理サーバーについて
サーバーの全体管理サーバーは、マスターまたは複数の単一のレプリカのシステムでは、中央管理サーバーが含まれるフロント エンド サーバーでデータベースの読み取り/書き込みコピーを保持する場所。 中央の管理サーバーを含むフロント エンド サーバーを含め、トポロジ内の各コンピューターには、中央管理ストア内のデータのセットアップ中にコンピューターにインストールされている SQL Server データベース (既定では RTCLOCAL という名前) の読み取り専用コピーし、展開します。 ローカル データベースは、すべてのコンピューターでサービスとして実行される Lync Server レプリカ レプリケーター エージェントを使用してレプリカの更新を受信します。 中央管理サーバーとローカルのレプリカには、実際のデータベースの名前は、XDS で、xds.mdf および xds.ldf ファイルの構成です。 Master データベースの場所は、Active Directory ドメイン サービスでサービス コントロール ポイント (SCP) によって参照されます。 中央管理サーバーを使用して管理し、Lync Server を構成するすべてのツールでは、SCP を使用して、中央管理ストアを探します。
  
## <a name="see-also"></a>関連項目

[移動 CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)