---
title: コール パーク アプリケーション設定の移行
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
description: 呼び出しパーク アプリケーションの移行には、従来のインストールでアップロードされたカスタムの保留音ファイルを使用して Skype for Business Server 2019 プールをプロビジョニングし、サービス レベル設定を復元し、すべてのコール パーク オービットを Skype for Business Server 2019 プールに再ターゲットします。 カスタマイズされた保留音ファイルがプールで構成されている場合は、これらのファイルを新しい 2019 プールにコピー Skype for Business Server必要があります。 さらに、コール パーク用にアップロードされたカスタマイズされた保留音ファイルの個別のバックアップ コピーを保持するために、コール パークのカスタマイズされた保留音ファイルを別の宛先にバックアップする必要があります。 コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。 プール ファイル ストアから 2019 年 2019 年Skype for Business Serverファイル ストアにオーディオ ファイルをコピーするには、次のパラメーターを使用して Xcopy コマンドを使用します。
ms.openlocfilehash: b8d2c5a898ca9ce4c2c1e8be4b9cbf3e7355a8cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597541"
---
# <a name="migrate-call-park-application-settings"></a>コール パーク アプリケーション設定の移行

コール パーク アプリケーションの移行には、従来のインストールでアップロードされたカスタムの保留音ファイルを使用して Skype for Business Server 2019 プールをプロビジョニングし、サービス レベルの設定を復元し、すべてのコール パーク オービットを Skype for Business Server 2019 プールに再ターゲットします。 カスタマイズされた保留音ファイルがプールで構成されている場合は、これらのファイルを新しい 2019 プールにコピー Skype for Business Server必要があります。 さらに、コール パーク用にアップロードされたカスタマイズされた保留音ファイルの個別のバックアップ コピーを保持するために、コール パークのカスタマイズされた保留音ファイルを別の宛先にバックアップする必要があります。 コール パーク アプリケーションのカスタマイズされた保留音ファイルは、プールのファイル ストアに格納されています。 プール ファイル ストアから 2019 年 2019 年の Skype for Business Server ファイル ストアにオーディオ ファイルをコピーするには、次のパラメーターを使用して **Xcopy** コマンドを使用します。 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

カスタマイズされたオーディオ ファイルすべてが Skype for Business Server 2019 ファイル ストアにコピーされている場合は、Skype for Business Server 2019 プールのコール パーク アプリケーション設定を構成し、レガシ プールに関連付けられているコール パーク オービット範囲を Skype for Business Server 2019 プールに再割り当てする必要があります。

コール パーク アプリケーションの設定には、ピックアップ タイムアウトのしきい値、保留音の有効化または無効化、通話ピックアップの最大試行回数、タイムアウト要求が含まれます。 **Set-CsCpsConfiguration** コマンドレットを実行するには、Skype for Business Server管理シェルを使用してコール パーク アプリケーション設定を管理する必要があります。 [コントロール パネル] コントロール パネルを使用してコール パーク アプリケーションSkype for Business Server管理できません。 

## <a name="reconfigure-the-call-park-service-settings"></a>Call Park Service の設定を再構成する

1. 2019 Skype for Business Server 2019 フロントエンド サーバーから、管理シェルSkype for Business Server開きます。

2. コマンドラインで、次のように入力します。

    > [!NOTE]
    > 2019 Skype for Business Server 2019 Call Park アプリケーションの設定が従来の設定と同じ場合は、この手順を省略できます。 Call Park アプリケーションの設定が 2019 および従来の環境Skype for Business Server異なる場合は、以下のコマンドレットをテンプレートとして使用して、これらの変更を更新します。 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

従来のプールから Skype for Business Server 2019 プールまでのすべてのコール パーク オービット範囲を再割り当てするには、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用できます。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用してすべてのコール パークオービット範囲Skype for Business Server割り当て

1. [コントロール Skype for Business Server] を開きます。

2. 左側のウィンドウで、[**音声機能**] を選択します。

3. [**コール パーク**] タブを選択します。 

4. 従来のプールに割り当てられたコール パーク オービット範囲ごとに、宛先サーバー設定の **FQDN** を編集し、コール パーク要求を処理する Skype for Business Server 2019 プールを選択します。 

5. [**コミット**] を選択して変更を保存します。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>管理シェルを使用してすべてのコール パークオービット範囲Skype for Business Server割り当て

1. [管理Skype for Business Server] を開きます。

2. コマンド ラインで、次のように入力します。

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    このコマンドレットを実行すると、展開内のコール パーク オービットの範囲がすべて表示されます。 **CallParkServiceId** パラメーターと **CallParkServerFqdn** パラメーターをレガシ プールとして設定しているすべてのコール パーク オービットを再割り当てする必要があります。 

    従来のコール パーク オービット範囲を 2019 Skype for Business Serverに再割り当てするには、コマンド ラインで次の値を入力します。

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

すべてのコール パーク オービット範囲を Skype for Business Server 2019 プールに再割り当てした後、コール パーク アプリケーションの移行プロセスが完了し、Skype for Business Server 2019 プールが将来のすべてのコール パーク要求を処理します。


