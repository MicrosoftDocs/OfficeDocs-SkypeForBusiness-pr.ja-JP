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
ms.openlocfilehash: d62a3af74607c3f4868ed1d808160556a765844f298ec889b37137b3133d8a30
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294214"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>サーバーのメンテナンスのために新Skype for Business Server接続を防止する


Skype for Business Serverを使用すると、ユーザーにサービスを失わずにサーバーをオフラインにできます (ソフトウェアやハードウェアのアップグレードを適用する場合など)。

プール内でサーバーへの新規接続および呼び出しを禁止するオプションを指定した場合、このオプションを実装するとすぐに新規接続および呼び出しを受け付けなくなります。これら新規の接続および呼び出しは、プール内の他のサーバーを介してルーティングされます。新規接続を禁止しているサーバーでは、既存の接続上のセッションは自然に終了するまで続行することができます。既存のセッションがすべて終了すると、サーバーをオフラインにすることができます。

フロント エンド サーバーへの新しい接続を防止する場合、一部の機能Skype for Business Serverサービスは、DNS 負荷分散に依存して正常に機能します。 プール内で DNS 負荷分散を使用していない場合、サーバーが新規接続を禁止している間、これらのサービスを介する接続はその他のサーバーに再ルーティングされない可能性があり、結果、サーバーがオフラインになる時、一部のセッションおよび通話が中断される可能性があります。 このオプションを確実に正しく動作させるために DNS 負荷分散を使用する機能は、次のとおりです。

  - Attendant

  - 会議アナウンス アプリケーション

  - 応答グループ アプリケーション

  - アナウンス アプリケーション

  - コール パーク アプリケーション

DNS 負荷分散の詳細については、「負荷分散 [要件」を参照してください](../../plan-your-deployment/network-requirements/load-balancing.md)。

サーバーが実行されているサーバー上のすべてのサービスに対する新しい接続をSkype for Business Server、個々のサービスに対する新しい接続をSkype for Business Serverすることもできます。 たとえば、このメソッドは、サーバー全体をシャットダウンする必要Skype for Business Server更新プログラムを適用する必要がある場合に役立ちます。 1 つのサービスに対して接続を禁止する場合、Windows のサービス一覧でグループ化され、表示されるサービスを選択する必要があります。 たとえば、Skype for Business Server Front-End サービスと監視用のデータ収集エージェントは別個の Skype for Business Server サービスですが、Windows サービスの一覧では、Skype for Business Server フロント エンド サービスとして統合され表示されます。 フロントエンド サービスの新しい接続をSkype for Business Serverできますが、これら 2 つの基になる 2 つのサービスに対する新しい接続を個別Skype for Business Serverすることはできません。

> [!IMPORTANT]
> 新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>ユーザーへの新しい接続を防止Skype for Business Server

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  サービス スナップイン コンソールを開きます:[**スタート**]をクリックし、[すべてのプログラム] をポイントし、[管理ツール] をポイントし、[サービス] を **クリックします**。

3.  一覧で、新しい接続をSkype for Business Server Windowsするサービスをダブルクリックします。

4.  [プロパティ] ダイアログ ボックスの [**サービスの状態: 開始**] で、[**一時停止**] をクリックします。

5.  オプションですが、[**スタートアップの種類**] の横の [**手動**] をクリックすることをお勧めします。
    
    > [!IMPORTANT]
    > 新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。
