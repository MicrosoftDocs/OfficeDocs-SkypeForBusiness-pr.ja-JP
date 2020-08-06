---
title: バージョンのサポート
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: ダイナミック サポートの構造とそのフェーズを含めた Microsoft Teams ミーティングのライフサイクル サポートの詳細について。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 196f4e7e6384ffa0f0d59478e1a0cb326bf4b984
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201191"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams ミーティング アプリ バージョンのサポート
 
Microsoft Teams ミーティング アプリは年に数回更新されます。 各更新プログラムは、一般提供 (GA) のリリース日から 12 か月間サポートされます。 テクニカル サポートは 12 か月を通して提供されます。 ただし、サポート体制は動的であり、最新バージョンの提供可能性によって次の 2 つのフェーズがあります。

- **サービス提供および重要な更新プログラム フェーズ** \- Microsoft Teams ミーティング アプリの最新バージョンを実行すると、*セキュリティおよびサービス提供*更新プログラムを含む定期更新プログラムを受け取ります。

- **セキュリティ更新プログラムのみフェーズ** \- Microsoft Teams ミーティング アプリの新しいバージョンがリリースされると、そのアプリの以前のバージョンのサポート レベルが、12 か月のライフサイクルの残りの*セキュリティ更新プログラムのみ*に削減されます。

> [!NOTE]
> 最新バージョンは、常に、サービス提供および重要な更新プログラム フェーズになります。 また、重要な更新プログラムが必要なコードの問題が発生した場合は、最新バージョンをインストールして修正プログラムを受け取る必要があります。 サポートされているその他のすべてのバージョンは、セキュリティ更新プログラムを受け取ることしかできません。

すべてのサポートは、バージョンの 12 か月のライフサイクルの終了後またはそれ以降に 2 つ以上の更新プログラムがリリースされた場合に終了します。 その後は、お客様が、サポートされているバージョンに更新する必要があります。

すべてのリリースが、[Microsoft Teams ミーティング リリース ノート](rooms-release-note.md)に記載されています。

## <a name="windows-10-release-support"></a>Windows 10 リリースのサポート

Microsoft Teams ミーティングには、半期のチャネル サービス オプションに基づく Windows 10 IoT Enterprise または Windows 10 Enterprise SKU が必要です。 その他の Windows 10 エディションはサポートされていません。

- Windows 10 Enterprise Long-Term Servicing Branch (LTSB)/長期サービス チャネル (LTSC) エディション
- Windows 10 Internet of Things (IoT) Enterprise LTSB/LTSC エディション
- Windows 10 Pro エディションや Windows 10 Home エディションなどの、その他の Windows エディション

Microsoft Teams ミーティング デバイスでは、Windows 10 機能更新プログラムが即座には提供または更新されません。 [Windows 10 リリース情報](https://docs.microsoft.com/windows/release-information/)ページで公開される一般提供日から最大 6 か月間の意図的な遅延。 遅延時間は、Windows 10 リリースの互換性を検証するために、Microsoft Teams ミーティング アプリケーション、デバイス ハードウェア、および認定オーディオ ビデオ周辺機器に使用されます。 Windows 10 のメジャー リリースの各開発期間に検証が開始され、継続されます。 すべてのデバイス メーカーが自分たちのデバイス用の最新イメージを構築したことを検証し、Microsoft Teams でそれらのイメージを認定してテストするための余分な時間が必要です。 検証期間中に、Microsoft Teams ミーティング アプリが、[Windows Update for Business グループ ポリシー](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)を使用して、Windows 10 の機能更新プログラムを遅延させます。 互換性の問題が発見され、解決されると、Microsoft Store での新しいアプリ リリースを通して、グループ ポリシーを更新することにより、ブロックが解除されます。 Microsoft Teams ミーティング アプリを実行するデバイスは、夜間のメンテナンス再起動中に、適切な Windows 10 リリースに自動的に更新されます。 手動で更新プログラムを管理する必要があるお客様は、MSI バージョンを使用できます。  

> [!IMPORTANT]
> 検証期間中は、Microsoft Teams ミーティング デバイスが、何らかの方法で、次の Windows 10 のリリースに更新**されない**ようにする必要があります。 これには、グループ ポリシーの施行の無効化または System Center やその他のサードパーティ製デバイス管理サービスの使用が含まれます。 これらのいずれかが原因で Microsoft Teams ミーティング アプリケーションの問題が発生したり、デバイスが使用できなくなったりすることがあります。  

次の表は、Microsoft Teams ミーティングのサポートが確認されている Windows 10 の推奨バージョンとサポート対象バージョンを示しています。 すべての日付は、ISO 8601 形式 (YYYY-MM-DD) で表示されます。

|バージョン  |提供日   |Microsoft Teams ミーティングのサポート状況   |Microsoft Teams ミーティングの最小アプリケーション バージョン | 推奨 OS ビルド  |
|:---  |:---       |:---                                  |:---     |:---     |
| 2004 |2020-05-27 |検証の下で、 <br/>非推奨|&#x2014; |19041.264 |
| 1909 |2019-11-12 |サポート済み、 <br/>推奨 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |サポート済み  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |スキップ、 <br/>非推奨 &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |サポート                             |4.1.22.0 |17134.191|
| 1709 |2018-01-18 |非サポート                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |非サポート                         |&#x2014; |&#x2014; |

&#x2780; Microsoft Teams ミーティング アプリケーションで互換性の問題が見つかったため、Windows 10 バージョン 1809 は非推奨になっています。 この特定の問題により、Microsoft Teams ミーティング アプリケーションは夜間に再起動すると失敗します。 この問題は、Windows 10 バージョン 1903 で解決されています。  

&#x2781; Microsoft Teams ミーティング アプリケーションで互換性の問題が見つかったため、Windows 10 バージョン 2004 は非推奨になっています。 この特定の問題により、Microsoft Teams ミーティング アプリケーションは夜間に再起動すると失敗します。 

Windows 10 のサポートされているバージョンを使用している場合は、Microsoft Teams ミーティング アプリの最新のアプリケーション更新プログラムを入手できます。  

## <a name="related-topics"></a>関連項目

[Microsoft Teams ミーティング ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams ミーティング リリース ノート](rooms-release-note.md)

[Microsoft Teams ミーティングを計画する](rooms-plan.md)
