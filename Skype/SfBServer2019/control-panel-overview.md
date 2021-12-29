---
title: コントロール パネル - 概要
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: この記事では、新しいコントロール パネルの概要について説明します。
ms.openlocfilehash: 7def5267b88260b66b6aa345c9585b83659f6ea3
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625938"
---
# <a name="control-panel"></a>コントロール パネル

現在のコントロール パネルは、レガシ コントロール パネルの新しいバージョンで、このコントロール パネルはタンデムで存在します。 新しいコントロール パネルは、2019 年 7 月の累積的な更新プログラムから存在しました。 これは、組織の環境内のサーバー、ユーザー、クライアント、およびデバイスの構成を管理するのに役立ちます。

従来のコントロール パネルは、Silverlight テクノロジが 2021 年 10 月 12 日に "サポートの終了" 段階に達した場合、機能しない場合があります。 詳細については [、「Silverlight End of Support」を参照してください](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)。

> [!NOTE]
> 従来のコントロール パネルの詳細については、「[](../SfbServer/management-tools/install-and-open-administrative-tools.md)コントロール パネル」を参照し、コントロール パネルのセクションSkype for Business Server **移動します**。

## <a name="access-control-panel"></a>アクセス コントロール パネル

ブラウザーで新しいコントロール パネルを起動するには、https://-FQDN/macp または構成済みの簡易 &lt; &gt; URL を入力します。

新しいコントロール パネルには、組織のほとんどのニーズをカバーする一般的に使用されるメニュー項目が含まれています。 従来のコントロール パネルから、新しいコントロール パネルで使用できないメニュー項目がいくつか存在します。 ただし、ユーザーが PowerShell コマンドレットを使用してこれらのメニュー項目の機能を利用するオプションがあります。 詳細については、以下の表を参照してください。

> [!NOTE]
> 他のメニュー項目のドキュメントは、段階的に後で使用できます。

## <a name="client"></a>クライアント

|サブメニュー  |コマンドレットの情報のソース  |
|---------|---------|
|クライアント バージョン ポリシー         |    [クライアント バージョン ポリシー](use-powershell-client-menu.md#client-version-policy)     |
|クライアント バージョンの構成      |  [クライアント バージョンの構成](use-powershell-client-menu.md#client-version-configuration)       |
|デバイス更新    | [デバイス更新](use-powershell-client-menu.md#device-update)        |
|テスト デバイス     | [テスト デバイス](use-powershell-client-menu.md#test-device)        |
|デバイス ログの構成         |    [デバイス ログの構成](use-powershell-client-menu.md#device-log-configuration)     |
|デバイス構成         |    [デバイス構成](use-powershell-client-menu.md#device-configuration)     |
|モビリティ ポリシー         |    [モビリティ ポリシー](use-powershell-client-menu.md#mobility-policy)     |
|プッシュ通知の構成         |    [プッシュ通知の構成](use-powershell-client-menu.md#push-notification-configuration)     |

## <a name="security"></a>セキュリティ

|サブメニュー  |コマンドレットの情報のソース  |
|---------|---------|
|レジストラー         |    [レジストラー](use-powershell-security-menu.md#registrar)     |
|(Web) サービス      |  [Web サービス](use-powershell-security-menu.md#web-service)       |
|PIN ポリシー    | [PIN ポリシー](use-powershell-security-menu.md#pin-policy)        |

## <a name="im-and-presence"></a>IM とプレゼンス

|サブメニュー  |コマンドレットの情報のソース  |
|---------|---------|
|ファイル フィルター         |    [ファイル フィルター](use-powershell-im-and-presence-menu.md#file-filter)     |
|URL フィルター      |  [URL フィルター](use-powershell-im-and-presence-menu.md#url-filter)       |

## <a name="monitoring-and-archiving"></a>監視およびアーカイブ

|サブメニュー  |コマンドレットの情報のソース  |
|---------|---------|
|通話詳細記録       |    [通話詳細記録](use-powershell-monitoring-and-archiving-menu.md#call-detail-recording)     |
|Quality of Experience Data      |  [Quality of Experience Data](use-powershell-monitoring-and-archiving-menu.md#quality-of-experience-data)       |
|アーカイブ ポリシー       |    [アーカイブ ポリシー](use-powershell-monitoring-and-archiving-menu.md#archiving-policy)     |
|アーカイブ構成      |  [アーカイブ構成](use-powershell-monitoring-and-archiving-menu.md#archiving-configuration)       |

## <a name="network-configuration"></a>ネットワーク構成

|サブメニュー  |コマンドレットの情報のソース  |
|---------|---------|
|場所ポリシー       |    [場所のポリシー](use-powershell-network-configuration-menu.md#location-policy)     |
|帯域幅ポリシー      |  [帯域幅ポリシー](use-powershell-network-configuration-menu.md#bandwidth-policy)       |
|地域       |    [Region](use-powershell-network-configuration-menu.md#region)     |
|サイト      |  [サイト](use-powershell-network-configuration-menu.md#site)       |
|サブネット      |  [Subnet](use-powershell-network-configuration-menu.md#subnet)       |
|地域リンク       |    [地域リンク](use-powershell-network-configuration-menu.md#region-link)     |
|地域ルート      |  [地域ルート](use-powershell-network-configuration-menu.md#region-route)       |

## <a name="topology"></a>トポロジ

|サブメニュー  |コマンドレットの情報のソース  |
|---------|---------|
|状態       |    [状態](use-powershell-topology-menu.md#status)     |
|サーバー アプリケーション      |  [サーバー アプリケーション](use-powershell-topology-menu.md#server-application)       |
|簡易 URL       |    [簡易 URL](use-powershell-topology-menu.md#simple-url)     |
|信頼済みアプリケーション       |    [信頼済みアプリケーション](use-powershell-topology-menu.md#trusted-application)     |
