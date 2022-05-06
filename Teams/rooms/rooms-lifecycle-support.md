---
title: Microsoft Teams Rooms アプリ バージョンのサポート
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ダイナミック サポートの構造とそのフェーズを含めた Microsoft Teams Rooms のライフサイクル サポートの詳細について。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2f1ad2ce3be71667588288b82ca93646ff776a5
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503674"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams Rooms アプリ バージョンのサポート
 
Microsoft Teams Rooms アプリは、Windows ストアを介して更新プログラムを取得します。 Microsoft Teams Room アプリでは常緑製品ライフサイクルが使用され、アプリの最新バージョンと最新バージョンのみがいつでもサポートされます。 Microsoft Teams Room アプリは、ルームの使用に合わせて変更されたTeams デスクトップ アプリの特定のバージョンをバンドルします。 Teams デスクトップ アプリは 2 週間ごとに更新されます。 [Teams更新プロセス](../teams-client-update.md)の詳細について説明します。 つまり、アプリの最新バージョンTeams Roomsデスクトップ アプリの更新は最大 6 Teams可能であるため、Teams Room アプリケーションを常にTeams Rooms アプリの最新バージョンに更新しておくことをお勧めします。 

Teams Roomsのサポート構造は動的であり、最新バージョンの可用性によって異なります。 最新ではないアプリケーションのバージョンでコードの欠陥が発生した場合は、修正プログラムを受け取るには、最新バージョンをインストールする必要があります。

すべてのリリースが、[Microsoft Teams Rooms リリース ノート](rooms-release-note.md)に記載されています。

> [!IMPORTANT]
> 古いバージョンのTeams ルーム アプリケーションに付属している新しいデバイスをインストールする場合は、アカウントを設定した後、Windows更新プログラムをダウンロードする前[に、アプリケーションを手動で更新](manual-update.md)することをお勧めします。 これにより、正しい OS バージョンとWindows更新プログラムがデバイスにインストールされます。  

## <a name="windows-10-release-support"></a>Windows 10 リリースのサポート

Microsoft Teams Rooms には、半期のチャネル サービス オプションに基づく Windows 10 IoT Enterprise または Windows 10 Enterprise SKU が必要です。 その他の Windows 10 エディションはサポートされていません。

- Windows 10 Enterprise Long-Term Servicing Branch (LTSB)/長期サービス チャネル (LTSC) エディション
- Windows 10 Internet of Things (IoT) Enterprise LTSB/LTSC エディション
- Windows 10 Pro エディションや Windows 10 Home エディションなどの、その他の Windows エディション

新しいWindows 10機能更新プログラムは、Microsoft Teams Rooms デバイスではすぐに提供されません。 Windows 10[リリース情報](/windows/release-information/)ページに公開された一般公開日から最大で 6 か月以上の意図的な遅延が発生します。 今回は、Microsoft Teams Rooms アプリ、デバイス ハードウェア、および認定オーディオ ビデオ周辺機器のWindows 10リリースの互換性を検証するために使用されます。 Windows 10 のメジャー リリースの各開発期間に検証が開始され、継続されます。 すべてのデバイス製造元がデバイス用に更新されたイメージを構築したことを検証し、Microsoft がそれらのイメージを認定してテストするには、余分な時間が必要です。 検証期間中、Microsoft Teams Room アプリは[ビジネス グループ ポリシーのWindows Update](/windows/deployment/update/waas-manage-updates-wufb)を使用して、Windows 10機能の更新を遅延させます。 互換性の問題が発見され、解決されると、Microsoft Store での新しいアプリ リリースを通して、グループ ポリシーを更新することにより、ブロックが解除されます。 Microsoft Teams Rooms アプリを実行するデバイスは、夜間のメンテナンス再起動中に、適切な Windows 10 リリースに自動的に更新されます。 MSI バージョンは、更新プログラムを手動で管理する必要があるお客様が利用できるようになります。  

> [!IMPORTANT]
> 検証期間中は、Microsoft Teams Rooms デバイスが、何らかの方法で、次の Windows 10 のリリースに更新 **されない** ようにする必要があります。 これには、グループ ポリシーの施行の無効化または System Center やその他のサードパーティ製デバイス管理サービスの使用が含まれます。 これらのいずれかが原因で、Microsoft Teams Room アプリの問題が発生したり、デバイスが使用できなくなる可能性があります。  

次の表は、Microsoft Teams Roomsのサポートが確認されている Windows 10 の推奨バージョンとサポート対象バージョンを示しています。 すべての日付は、ISO 8601 形式 (YYYY-MM-DD) で表示されます。

|バージョン  |提供日   |Microsoft Teams Rooms のサポート状況   |Microsoft Teams Rooms の最小アプリケーション バージョン | 推奨 OS ビルド  |
|:---  |:---       |:---                                  |:---     |:---     |
| 21H1 |2021-05-18 |非サポート                         |&#x2014; |&#x2014; |
| 20H2 |2020-10-20 |サポート済み、 <br/>推奨|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |スキップ、 <br/> 非推奨 &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |サポート |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |非サポート  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |サポートされていません。 <br/>既知の互換性の問題&#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |非サポート                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |非サポート                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |非サポート                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 バージョン 2004 は、Microsoft Teams Rooms アプリケーションとの互換性の問題が原因で推奨されません。 この特定の問題により、Microsoft Teams Rooms アプリケーションは夜間に再起動すると失敗します。 

&#x2781; Windows 10 バージョン 1809 は、Microsoft Teams Rooms アプリケーションとの互換性の問題が原因で推奨されません。 この特定の問題により、Microsoft Teams Rooms アプリケーションは夜間に再起動すると失敗します。 この問題は、Windows 10 バージョン 1903 で解決されています。  

Windows 10 のサポートされているバージョンを使用している場合は、Microsoft Teams Rooms アプリの最新のアプリケーション更新プログラムを入手できます。  


## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms リリース ノート](rooms-release-note.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
