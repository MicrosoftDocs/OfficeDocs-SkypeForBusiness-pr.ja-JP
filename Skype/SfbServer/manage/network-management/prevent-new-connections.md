---
title: 新しい接続を禁止する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b7aa303f2b49a806434af91789ab3e610fdc45c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279488"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>サーバーメンテナンスのための Skype for Business Server への新しい接続を禁止する


Skype for Business Server を使用すると、サービスが失われることなく、サーバーをオフラインにして (ソフトウェアやハードウェアのアップグレードを適用するなど) することができます。

プール内のサーバーへの新しい接続または呼び出しを禁止するオプションを指定すると、このオプションを実装するとすぐに、新しい接続と通話の取得が停止されます。 これらの新しい接続と通話は、プール内の他のサーバーを経由してルーティングされます。 新しい接続を禁止しているサーバーでは、既存の接続に対するセッションは自然に終了するまで続行されます。 既存のすべてのセッションが終了したら、サーバーをオフラインにすることができます。

フロントエンドサーバーへの新しい接続を禁止する場合、一部の Skype for Business Server の機能とサービスは、適切に動作するように DNS の負荷分散を利用します。 プールで DNS の負荷分散を使用していない場合、サーバーが新しい接続を妨害している期間中、これらのサービスからの接続が他のサーバーに再ルーティングされないことがあります。そのため、サーバーがオフラインになったときに、一部のセッションと通話がまし. このオプションが適切に動作するように、DNS の負荷分散に依存する機能は次のように動作します。

  - Attendant

  - 会議アナウンス アプリケーション

  - 応答グループ アプリケーション

  - アナウンス アプリケーション

  - コール パーク アプリケーション

DNS 負荷分散の詳細については、「[負荷分散の要件](../../plan-your-deployment/network-requirements/load-balancing.md)」を参照してください。

Skype for Business Server を実行しているサーバー上のすべてのサービスの新しい接続を防止するだけでなく、個々の Skype for Business Server サービスへの新しい接続を防ぐこともできます。 たとえば、この方法は、サーバー全体をシャットダウンする必要がない Skype for Business Server の更新プログラムを適用する必要がある場合に役立ちます。 1つのサービスに対する接続を禁止する場合は、サービスがグループ化され、サービスの一覧に表示されるサービスを選択する必要があることに注意してください。 たとえば、Skype for Business Server のフロントエンドサービスと監視用のデータ収集エージェントは、別々の Skype for Business Server サービスですが、Windows services のリストで統合され、Skype for Business Server のフロントエンドとして表示されます。サービス. Skype for Business Server のフロントエンドサービスへの新しい接続を禁止することはできますが、これらの2つの個別の Skype for Business Server サービスへの新しい接続を個別に禁止することはできません。

> [!IMPORTANT]
> 新しい接続を禁止するようにサーバーを設定してから、サーバーを再起動すると、既定では、サーバーは起動後に新しい接続の受け入れを直します。 これを防ぐには、サーバーを再起動する前に、手動で一時停止および再開するようにサーバーを設定します。

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Skype for Business Server への新しい接続を禁止するには

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  [サービス] スナップインコンソールを開きます。 [**スタート**] をクリックし、[**すべてのプログラム**] をポイントして、[**管理ツール**] をポイントし、[**サービス**] をクリックします。

3.  リストで、新しい接続を禁止する Skype for Business Server Windows サービスをダブルクリックします。

4.  [プロパティ] ダイアログボックスの [**サービスの状態: 開始**] で、[**一時停止**] をクリックします。

5.  必要に応じて、[**スタートアップの種類**] の横にある [**手動**] をクリックします。
    
    > [!IMPORTANT]
    > 新しい接続を禁止するようにサーバーを設定してから、サーバーを再起動すると、既定では、サーバーは起動後に新しい接続の受け入れを直します。 これを防ぐには、サーバーを再起動する前に、手動で一時停止および再開するようにサーバーを設定します。
