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
ms.localizationpriority: medium
description: 2019 年 2019 年の移行Skype for Business Serverサポートされている移行手順は、サイド バイ サイド移行です。 このトピックでは、サイド バイ サイド移行を使用する理由について説明し、共存のテストに関する情報も示します。
ms.openlocfilehash: 4ca0e8d1362c05e87c4ec347115f7e45457c55d1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613396"
---
# <a name="migration-process"></a>移行のプロセス

2019 年 2019 年の移行Skype for Business Serverサポートされている移行手順は、サイド バイ サイド移行です。 このトピックでは、サイド バイ サイド移行を使用する理由について説明し、共存のテストに関する情報も示します。
  
## <a name="side-by-side-migration"></a>サイド バイ サイド移行

ほとんどすべての移行では、サイド バイ サイド移行パスの使用をお勧めします。 サイド バイ サイド移行では、Skype for Business Server 2019 の新しいサーバーを、以前のバージョンを実行している対応するサーバーと共に展開し、新しいサーバーに操作を転送します。 以前のバージョンにロールバックする必要がある場合は、操作を元のサーバーに戻す必要があります。 ただし、この状況では、アップグレードされたクライアントによって新しい会議がスケジュールされていた場合、それらの会議がすべて機能しなくなるのでクライアントのダウングレードも必要になります。
  
## <a name="coexistence-testing"></a>共存のテスト

以前のバージョンと並行して Skype for Business Server 2019 を展開した後、展開は Skype for Business Server 2019 と以前のバージョンの共存テスト状態を表します。 この状態のときに、サービスが開始されていること、各サイトを管理できること、クライアントが現在および従来のユーザーと通信できることをテストして確認することが重要です。 すべてのユーザーを移行する前に、各展開の状態を把握し、各展開が適切に機能および動作することを確認する必要があります。 通常、共存テストフェーズは、2019 年のパイロット テストSkype for Business Serverされます。 従来のユーザーはSkype for Business Server 2019 に移動され、アプリケーションの互換性と機能が正しく動作します。 パイロット テストの後、ユーザーとアプリケーションは Skype for Business Server 2019 の実稼働バージョンに移動され、以前のバージョンの従来のプールとアプリケーションは廃止されます。
  
