---
title: 移行のプロセス
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
description: Skype for Business Server 2019 の推奨およびサポートされている移行手順は、並行して移行されます。 このトピックでは、サイド バイ サイド移行を使用する理由について説明し、共存のテストに関する情報も示します。
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752639"
---
# <a name="migration-process"></a>移行のプロセス

Skype for Business Server 2019 の推奨およびサポートされている移行手順は、並行して移行されます。 このトピックでは、サイド バイ サイド移行を使用する理由について説明し、共存のテストに関する情報も示します。
  
## <a name="side-by-side-migration"></a>サイド バイ サイド移行

ほとんどすべての移行では、サイド バイ サイド移行パスの使用をお勧めします。 Side-by-side 移行では、以前のバージョンを実行している対応するサーバーと共に、Skype for Business Server 2019 と共に新しいサーバーを展開し、新しいサーバーに操作を転送します。 以前のバージョンにロールバックする必要が生じた場合は、元のサーバーに戻す操作のみを実行する必要があります。 ただし、この状況では、アップグレードされたクライアントによって新しい会議がスケジュールされていた場合、それらの会議がすべて機能しなくなるのでクライアントのダウングレードも必要になります。
  
## <a name="coexistence-testing"></a>共存のテスト

以前のバージョンと並行して Skype for Business Server 2019 を展開した後、展開は、Skype for Business Server 2019 と以前のバージョンの共存テストの状態を表します。 この状態のときに、サービスが開始されていること、各サイトを管理できること、クライアントが現在および従来のユーザーと通信できることをテストして確認することが重要です。 すべてのユーザーを移行する前に、各展開の状態を把握し、各展開が適切に機能および動作することを確認する必要があります。 通常、Skype for Business Server 2019 のパイロットテストにおいて、共存のテスト段階が存在します。 従来のユーザーは、アプリケーションの互換性と機能が正しく動作していることを確認するために、長期間 Skype for Business Server 2019 に移動されます。 パイロットテストの後、ユーザーとアプリケーションが Skype for Business Server 2019 の運用バージョンに移行され、以前のバージョンの従来のプールとアプリケーションは廃止されます。
  
