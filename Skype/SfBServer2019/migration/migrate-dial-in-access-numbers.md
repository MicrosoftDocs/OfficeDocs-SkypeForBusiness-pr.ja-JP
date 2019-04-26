---
title: ダイヤルイン アクセス番号の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 の Skype に移行するダイヤルイン アクセス番号は、連絡先オブジェクトを移行するのには移動 CsApplicationEndpoint コマンドレットを実行する必要があります。 従来のインストールと Skype ビジネス サーバー 2019 共存の期間には、ビジネス サーバー 2019 の Skype で作成したダイヤルイン アクセス番号と同様に動作では、従来のインストールでは、作成するダイヤルイン アクセス番号これで説明するようセクションです。
ms.openlocfilehash: 7f7aef113018a27e70b88e166d365195c07dce9c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239584"
---
# <a name="migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号の移行

ビジネス サーバー 2019 の Skype に移行するダイヤルイン アクセス番号は、連絡先オブジェクトを移行するのには**移動 CsApplicationEndpoint**コマンドレットを実行する必要があります。 従来のインストールと Skype ビジネス サーバー 2019 共存の期間には、ビジネス サーバー 2019 の Skype で作成したダイヤルイン アクセス番号と同様に動作では、従来のインストールでは、作成するダイヤルイン アクセス番号これで説明するようセクションです。 

従来で作成したダイヤルイン アクセス番号は、インストールがビジネス サーバー 2019、またはの前に、ビジネスのサーバー 2019、Skype で作成した Skype を移動中、または移行後に、次の特徴があります。

- Office 通信 Server 2007 の R2 の会議出席依頼とダイヤルイン アクセス番号のページには表示されません。

- レガシー インストールの会議出席依頼とダイヤルイン アクセス番号のページに表示されます。

- Skype のビジネス サーバー 2019 会議出席依頼とダイヤルイン アクセス番号のページが表示されます。

- 表示したり、Office 通信 Server 2007 の R2 の管理ツールで変更することはできません。

- 表示およびレガシー インストールのコントロール パネルと従来のインストール管理シェルを変更できます。

- 表示およびビジネス サーバー 2019 のコントロール パネルの Skype と Skype ビジネス サーバー 2019 の管理シェルを変更できます。

- 再シーケンス処理できる領域内にある優先順位のパラメーターを使用してセット CsDialinConferencingAccessNumber コマンドレットを使用しています。

移行を完了する必要がありますポイントには、従来のダイヤルイン アクセス番号がレガシー インストールのプールの使用を停止する前に、プールをインストールします。 次の手順に従って、ダイヤルイン アクセス番号の移行を完了しないと、アクセス番号への着信呼び出しが失敗します。

> [!IMPORTANT]
> レガシー インストールのプールの使用を停止する前にこの手順を実行する必要があります。 

> [!NOTE]
> サービスの停止の期間が短い場合に、ネットワーク使用率が軽いときは、ダイヤルイン アクセス番号を移動することをお勧めします。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>番号を特定しをダイヤルイン アクセスを移動するには

1. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。

2. 各ダイヤルイン アクセス番号をビジネス サーバー 2019 の Skype 上でホストされているプールに移動すると、コマンド ・ ラインから実行します。 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Skype をビジネス サーバーのコントロール パネルを開きます。

4. 左側のナビゲーション バーで [**会議**] をクリックします。

5. **ダイヤルイン アクセス番号**] タブをクリックします。 

6. ないダイヤルイン アクセス番号のまま移行しているレガシー インストールのプールのことを確認します。

    > [!NOTE]
    > すべてのダイヤルイン アクセス番号は、ビジネス サーバー 2019 プールの Skype をポイントして、レガシー インストールのプールをし、解除できます。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用してダイヤルイン アクセス番号の移行を検証します。

1. **CsUserAdministrator**または**CsAdministrator**の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 

2. Skype をビジネス サーバーのコントロール パネルを開きます。

3. 左側のナビゲーション バーで [**会議**] をクリックします。

4. **ダイヤルイン アクセス番号**] タブをクリックします。 

5. ビジネス サーバー 2019 の Skype 上でホストされているプールに、すべてのダイヤルイン アクセス番号が移行されたことを確認します。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>ビジネス サーバー管理シェルの Skype を使用してダイヤルイン アクセス番号の移行を検証します。

1. Skype をビジネス サーバー管理シェルを開きます。

2. すべてを取得するのには、ダイヤルイン会議アクセス番号移行、実行コマンド ・ ラインから。

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. ビジネス サーバー 2019 の Skype 上でホストされているプールに、すべてのダイヤルイン アクセス番号が移行されたことを確認します。


