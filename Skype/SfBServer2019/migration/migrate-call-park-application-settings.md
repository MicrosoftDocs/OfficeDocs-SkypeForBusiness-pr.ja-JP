---
title: コール パーク アプリケーション設定の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: コールパークアプリケーションの移行には、Skype for Business Server 2019 プールのプロビジョニングが含まれています。このファイルには、従来のインストールでアップロードされたカスタム音楽が含まれています。また、サービスレベル設定を復元して、orbits の retargetingSkype for Business Server 2019 プール。 カスタマイズした音楽の保留中のファイルがプールで構成されている場合は、これらのファイルを新しい Skype for Business Server 2019 プールにコピーする必要があります。 さらに、コールパーク用にアップロードされた、カスタマイズされた音楽の保存ファイルを別の場所にバックアップしておくことをお勧めします。これは、コールパーク用にアップロードされたカスタマイズされた音楽の保存ファイルの個別のバックアップコピーを保持するためです。 コールパークアプリケーション用にカスタマイズされた音楽保留のファイルは、プールのファイルストアに保存されます。 プールファイルストアから Skype for Business Server 2019 ファイルストアにオーディオファイルをコピーするには、次のパラメーターを使用して Xcopy コマンドを使用します。
ms.openlocfilehash: aa4ac3cfbe6802b8853a8ec8886f8fffe1a20a51
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280832"
---
# <a name="migrate-call-park-application-settings"></a>コール パーク アプリケーション設定の移行

コールパークアプリケーションの移行には、Skype for Business Server 2019 プールのプロビジョニングが含まれます。このファイルには、従来のインストールでアップロードされたカスタムの音楽の保存ファイルが含まれています。サービスレベルの設定を復元して、すべてのコールパーク orbits を再ターゲット化します。Skype for Business Server 2019 プール。 カスタマイズした音楽の保留中のファイルがプールで構成されている場合は、これらのファイルを新しい Skype for Business Server 2019 プールにコピーする必要があります。 さらに、通話パークをカスタマイズして、コールパーク用にアップロードされたカスタマイズされた音楽の保存ファイルを別の場所に保存することをお勧めします。 コールパークアプリケーション用にカスタマイズされた音楽保留のファイルは、プールのファイルストアに保存されます。 プールファイルストアから Skype for Business Server 2019 ファイルストアにオーディオファイルをコピーするには、次のパラメーターを使用して**Xcopy**コマンドを使用します。 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

カスタマイズされたすべてのオーディオファイルが Skype for Business Server 2019 ファイルストアにコピーされると、Skype for Business Server 2019 プールのコールパークアプリケーションの設定が構成され、従来のプールと関連付けられている範囲がコールパークで呼び出されます。Skype for Business Server 2019 プールに再割り当てする必要があります。

コールパークアプリケーションの設定には、ピックアップタイムアウトしきい値、保留中の音楽を有効または無効にする、最大通話ピックアップ試行回数、タイムアウト要求が含まれます。 **CsCpsConfiguration**コマンドレットを実行するには、Skype For Business Server 管理シェルを使用して、コールパークアプリケーションの設定を管理する必要があります。 Skype for Business Server コントロールパネルを使用して、コールパークアプリケーションの設定を管理することはできません。 

## <a name="reconfigure-the-call-park-service-settings"></a>コールパークサービス設定を再構成する

1. Skype for Business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。

2. コマンドラインで、次のように入力します。

    > [!NOTE]
    > Skype for Business Server 2019 Call パークのアプリケーション設定が従来の設定と同じである場合は、この手順をスキップできます。 コールパークアプリケーションの設定が Skype for Business Server 2019 と従来の環境で異なる場合は、次のコマンドレットをテンプレートとして使用して、それらの変更を更新します。 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

すべてのコールパークを、従来のプールから Skype for Business Server 2019 プールに再割り当てするには、Skype for Business Server コントロールパネルまたは Skype for Business Server の管理シェルを使用します。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してすべてのコールパークの範囲を再割り当てする

1. Skype for Business Server コントロールパネルを開きます。

2. 左側のウィンドウで、[**音声機能**] を選択します。

3. [ **Call パーク**] タブを選択します。 

4. 従来のプールに割り当てられている各通話パークの範囲は、[**宛先サーバーの FQDN** ] の設定を編集し、コールパーク要求を処理する Skype For business server 2019 プールを選択します。 

5. [**コミット**] を選んで変更を保存します。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してすべてのコールパーク範囲を再割り当てする

1. Skype for Business Server 管理シェルを開きます。

2. コマンドラインで、次のように入力します。

   ```
   Get-CsCallParkOrbit
   ```

    このコマンドレットは、展開内のすべてのコールパーク範囲の範囲を一覧表示します。 **CallParkServiceId**と**Callparkserverfqdn**パラメーターが設定されているすべての Call パーク orbits は、再割り当てする必要があります。 

    従来のコールパークの範囲を Skype for Business Server 2019 プールに再割り当てするには、コマンドラインで次のように入力します。

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

すべてのコールパークの範囲を Skype for Business Server 2019 プールに再割り当てした後、コールパークアプリケーションの移行プロセスが完了し、Skype for Business Server 2019 プールは、今後のすべてのコールパーク要求を処理します。


