---
title: 新しい接続の防止
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823467"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>サーバーメンテナンスのために Skype for Business Server への新しい接続を防止する


Skype for Business Server を使用すると、ユーザーにサービスを失わずにサーバーをオフラインにできます (ソフトウェアやハードウェアのアップグレードを適用する場合など)。

プール内でサーバーへの新規接続および呼び出しを禁止するオプションを指定した場合、このオプションを実装するとすぐに新規接続および呼び出しを受け付けなくなります。これら新規の接続および呼び出しは、プール内の他のサーバーを介してルーティングされます。新規接続を禁止しているサーバーでは、既存の接続上のセッションは自然に終了するまで続行することができます。既存のセッションがすべて終了すると、サーバーをオフラインにすることができます。

フロント エンド サーバーへの新しい接続を防ぐ場合、Skype for Business Server の一部の機能とサービスは DNS 負荷分散に依存して正しく機能します。 プール内で DNS 負荷分散を使用していない場合、サーバーが新規接続を禁止している間、これらのサービスを介する接続はその他のサーバーに再ルーティングされない可能性があり、結果、サーバーがオフラインになる時、一部のセッションおよび通話が中断される可能性があります。 このオプションを確実に正しく動作させるために DNS 負荷分散を使用する機能は、次のとおりです。

  - Attendant

  - 会議アナウンス アプリケーション

  - 応答グループ アプリケーション

  - アナウンス アプリケーション

  - コール パーク アプリケーション

DNS 負荷分散の詳細については、「負荷分散の要件 [」を参照してください](../../plan-your-deployment/network-requirements/load-balancing.md)。

Skype for Business Server を実行しているサーバー上のすべてのサービスに対して新しい接続を防止できるだけでなく、個々の Skype for Business Server サービスに対する新しい接続を防止することもできます。 たとえば、このメソッドは、サーバー全体のシャットダウンを必要としない Skype for Business Server 更新プログラムを適用する必要がある場合に便利です。 1 つのサービスに対して接続を禁止する場合、Windows のサービス一覧でグループ化され、表示されるサービスを選択する必要があります。 たとえば、Skype for Business Server Front-End サービスと監視用のデータ収集エージェントは個別の Skype for Business Server サービスですが、Windows サービスの一覧では、これらは統合され、Skype for Business Server フロントエンド サービスとして表示されます。 Skype for Business Server フロント エンド サービスの新しい接続を防止できますが、これら 2 つの個別の基礎となる Skype for Business Server サービスに対する新しい接続を個別に防止することはできません。

> [!IMPORTANT]
> 新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Skype for Business Server への新しい接続を防止するには

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  サービス スナップイン コンソールを開きます **。[スタート**]ボタンをクリックし、[すべてのプログラム] をポイントし、[管理ツール] をポイントして、[サービス] をクリック **します**。

3.  一覧で、新しい接続を防止する Skype for Business Server Windows サービスをダブルクリックします。

4.  [プロパティ] ダイアログ ボックスの [**サービスの状態: 開始**] で、[**一時停止**] をクリックします。

5.  オプションですが、[**スタートアップの種類**] の横の [**手動**] をクリックすることをお勧めします。
    
    > [!IMPORTANT]
    > 新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。
