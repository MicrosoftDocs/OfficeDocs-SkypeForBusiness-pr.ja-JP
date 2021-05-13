---
title: Microsoft Teams Rooms アプリ バージョンのサポート
ms.author: dstrome
author: dstrome
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
description: ダイナミック サポートの構造とそのフェーズを含めた Microsoft Teams Rooms のライフサイクル サポートの詳細について。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6ac865a59f2342b97ddb8cb0ae5807427c10b85
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469679"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams Rooms アプリ バージョンのサポート
 
Microsoft Teams Rooms アプリは年に数回更新されます。 各更新プログラムは、一般公開 (GA) リリース日から 12 か月間サポートされます。 テクニカル サポートは 12 か月を通して提供されます。 ただし、サポート体制は動的であり、最新バージョンの提供可能性によって次の 2 つのフェーズがあります。

- **サービスと重要な更新** プログラムのフェーズ - Microsoft Teams ミーティング アプリの最新バージョンを実行すると、セキュリティとサービスの更新プログラムを含む定期的な更新 *プログラムを受け取* る。

- **セキュリティ更新プログラムのみ** フェーズ - Microsoft Teams ミーティング アプリの新しいバージョンがリリースされた場合、以前のバージョンのアプリでは、12か月のライフサイクルの残りの部分についてのみ、セキュリティ更新プログラムによるサポート レベルが低下します。

> [!NOTE]
> 最新バージョンは、常に、サービス提供および重要な更新プログラム フェーズになります。 また、重要な更新プログラムが必要なコードの問題が発生した場合は、最新バージョンをインストールして修正プログラムを受け取る必要があります。 サポートされているその他のすべてのバージョンは、セキュリティ更新プログラムを受け取ることしかできません。

すべてのサポートは、バージョンの 12 か月のライフサイクルの終了後またはそれ以降に 2 つ以上の更新プログラムがリリースされた場合に終了します。 その後は、お客様が、サポートされているバージョンに更新する必要があります。

すべてのリリースが、[Microsoft Teams Rooms リリース ノート](rooms-release-note.md)に記載されています。

## <a name="windows-10-release-support"></a>Windows 10 リリースのサポート

Microsoft Teams Rooms には、半期のチャネル サービス オプションに基づく Windows 10 IoT Enterprise または Windows 10 Enterprise SKU が必要です。 その他の Windows 10 エディションはサポートされていません。

- Windows 10 Enterprise Long-Term Servicing Branch (LTSB)/長期サービス チャネル (LTSC) エディション
- Windows 10 Internet of Things (IoT) Enterprise LTSB/LTSC エディション
- Windows 10 Pro エディションや Windows 10 Home エディションなどの、その他の Windows エディション

新Windows 10機能の更新プログラムは、デバイスのMicrosoft Teams ミーティング提供されません。 [Windows 10 リリース情報](/windows/release-information/)ページで公開される一般提供日から最大 6 か月間の意図的な遅延。 遅延時間は、Windows 10 アプリ、デバイス ハードウェア、認定されたオーディオ ビデオ周辺機器のMicrosoft Teams ミーティング互換性を検証するために使用されます。 Windows 10 のメジャー リリースの各開発期間に検証が開始され、継続されます。 すべてのデバイス メーカーが自分たちのデバイス用の最新イメージを構築したことを検証し、Microsoft Teams でそれらのイメージを認定してテストするための余分な時間が必要です。 検証期間中、Microsoft Teams Room アプリでは、Windows [Update for Business](/windows/deployment/update/waas-manage-updates-wufb)グループ ポリシーを使用して、機能の更新Windows 10遅延します。 互換性の問題が発見され、解決されると、Microsoft Store での新しいアプリ リリースを通して、グループ ポリシーを更新することにより、ブロックが解除されます。 Microsoft Teams Rooms アプリを実行するデバイスは、夜間のメンテナンス再起動中に、適切な Windows 10 リリースに自動的に更新されます。 手動で更新プログラムを管理する必要があるお客様は、MSI バージョンを使用できます。  

> [!IMPORTANT]
> 検証期間中は、Microsoft Teams Rooms デバイスが、何らかの方法で、次の Windows 10 のリリースに更新 **されない** ようにする必要があります。 これには、グループ ポリシーの施行の無効化または System Center やその他のサードパーティ製デバイス管理サービスの使用が含まれます。 これらが原因で、Microsoft Teams Room アプリの問題が発生したり、デバイスが使用できなくなる可能性があります。  

次の表は、Microsoft Teams Roomsのサポートが確認されている Windows 10 の推奨バージョンとサポート対象バージョンを示しています。 すべての日付は、ISO 8601 形式 (YYYY-MM-DD) で表示されます。

|バージョン  |提供日   |Microsoft Teams Rooms のサポート状況   |Microsoft Teams Rooms の最小アプリケーション バージョン | 推奨 OS ビルド  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |サポート済み、 <br/>推奨|4.8.31.0 |19042.631 |
| 2004 |2020-05-27 |スキップ、 <br/> 非推奨 &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |サポート |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |非サポート  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |サポートされていません。 <br/>既知の互換性の問題&#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |非サポート                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |非サポート                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |非サポート                         |&#x2014; |&#x2014; |

&#x2780; Windows 10アプリケーションとの互換性の問題が見つかったので、バージョン 2004 Microsoft Teams ミーティングできません。 この特定の問題により、Microsoft Teams Rooms アプリケーションは夜間に再起動すると失敗します。 

&#x2781; Windows 10アプリケーションとの互換性の問題が見つかったので、バージョン 1809 Microsoft Teams ミーティングできません。 この特定の問題により、Microsoft Teams Rooms アプリケーションは夜間に再起動すると失敗します。 この問題は、Windows 10 バージョン 1903 で解決されています。  

Windows 10 のサポートされているバージョンを使用している場合は、Microsoft Teams Rooms アプリの最新のアプリケーション更新プログラムを入手できます。  

> [!IMPORTANT]
> 互換性Windows 10、次の 20H2 更新プログラムTeams ミーティングデバイスではまだ使用できません。 デバイス OEM は、できるだけ早くこれらの問題の解決に取り組む予定です。 Windows 10 20H2 は、これらのデバイスでは提供されません。 グループ ポリシー オブジェクト (GPO) またはモバイル デバイス管理 (MDM) をオーバーライドして、これらのデバイスを手動で 20H2 に更新することはできません。 
> 
> 互換性に問題があるデバイスは次のとおりです。
> 
> - HP Elite Slice
> - HP Elite Slice G2 MS SRS Audio Ready
> - HP Elite Slice MS SRS Partner Ready
> - HP Elite Slice G2 with MS(MS)
> - クUC-Engine (BIOS バージョン/日付に "KYSKLI" が含まれている - ときどきの BIOS を示す) 

## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms リリース ノート](rooms-release-note.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
