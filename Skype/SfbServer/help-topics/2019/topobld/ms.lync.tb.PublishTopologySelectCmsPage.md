---
title: トポロジの公開での CMS の選択ページ
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーを使用して構成したトポロジを公開します。 サーバーの全体管理ストアを保持する役割を担うフロント エンド サーバーまたはフロント エンド プールを一覧から選択する必要があります。 この役割をいつでも保持できるのは、フロント エンド サーバーまたはフロントエンド プールの 1 つのみです。
ms.openlocfilehash: 4f4658b13a634d5f1d231d4e8fe7683b3fc38b8f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860564"
---
# <a name="publish-topology-select-cms-page"></a>トポロジの公開での CMS の選択ページ
 
トポロジ ビルダーを使用して構成したトポロジを公開します。 サーバーの全体管理ストアを保持する役割を担うフロント エンド サーバーまたはフロント エンド プールを一覧から選択する必要があります。 この役割をいつでも保持できるのは、フロント エンド サーバーまたはフロントエンド プールの 1 つのみです。 
  
### <a name="about-the-central-management-server"></a>サーバーの全体管理について
中央管理サーバーは単一のマスター/複数レプリカ システムで、データベースの読み取り/書き込みコピーは、中央管理サーバーを含むフロントエンド サーバーによって保持されます。 サーバーの全体管理サーバーを含むフロントエンド サーバーを含むトポロジ内の各コンピューターには、セットアップと展開中に、SQL Server データベース (既定では RTCLOCAL という名前) にインストールされている中央管理ストア データの読み取り専用コピーがあります。 ローカル データベースは、すべてのコンピューターでサービスとして実行される Lync Server レプリカ レプリケーター エージェントを使用してレプリカ更新プログラムを受信します。 サーバーの全体管理サーバーとローカル レプリカ上の実際のデータベースの名前は、xds.mdf ファイルと xds.ldf ファイルで構成される XDS です。 マスター データベースの場所は、Active Directory ドメイン サービスのサービス コントロール ポイント (SCP) によって参照されます。 サーバーの全体管理サーバーを使用して Lync Server を管理および構成するツールはすべて、SCP を使用して中央管理ストアを検索します。
  
## <a name="see-also"></a>関連項目

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)