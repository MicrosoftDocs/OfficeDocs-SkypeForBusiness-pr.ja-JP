---
title: 移行のプロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 の推奨およびサポートされている移行手順は、並行して移行されます。 このトピックでは、サイドバイサイド移行を使用する必要がある理由と、共存テストに関する情報も含まれている理由について説明します。
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813415"
---
# <a name="migration-process"></a>移行のプロセス

Skype for Business Server 2019 の推奨およびサポートされている移行手順は、並行して移行されます。 このトピックでは、サイドバイサイド移行を使用する必要がある理由と、共存テストに関する情報も含まれている理由について説明します。
  
## <a name="side-by-side-migration"></a>サイドバイサイド移行

ほぼすべての移行では、並列移行パスを使用する必要があります。 並行して移行する場合は、以前のバージョンを実行しているサーバーと共に、Skype for Business Server 2019 と共に新しいサーバーを展開してから、新しいサーバーに操作を転送します。 以前のバージョンにロールバックする必要がある場合は、元のサーバーに戻す操作のみを行うことができます。 この状況では、アップグレードされたクライアントによってスケジュールされた新しい会議が機能しなくなり、クライアントもダウングレードされる必要があることに注意してください。
  
## <a name="coexistence-testing"></a>共存テスト

以前のバージョンと並行して Skype for Business Server 2019 を展開した後、展開は、Skype for Business Server 2019 と以前のバージョンの共存テストの状態を表します。 この状態では、サービスが開始されていること、各サイトが管理可能であること、クライアントが現在のユーザーと従来のユーザーと通信できることをテストして確認することが重要です。 すべてのユーザーを移行する前に、展開の状態を理解し、各展開が正常に機能して動作していることを確認することが非常に重要です。 通常、共存テストのフェーズは、Skype for Business Server 2019 のパイロットテストを通じて行われます。 従来のユーザーは、アプリケーションの互換性と機能が正しく動作していることを確認するため、Skype for Business Server 2019 に一定の期間移動されます。 パイロットテストの後、ユーザーとアプリケーションは、Skype for Business Server 2019 の運用バージョンに移行され、以前のバージョンの従来のプールとアプリケーションは廃止されます。
  
