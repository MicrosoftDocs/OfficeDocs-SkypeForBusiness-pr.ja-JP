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
ms.localizationpriority: medium
description: ダイナミック サポートの構造とそのフェーズを含めた Microsoft Teams Rooms のライフサイクル サポートの詳細について。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e7a82d7643a925d5c997c9d6fe5661a421d47ab
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356425"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams Rooms アプリ バージョンのサポート
 
Microsoft Teams Rooms アプリは、ストアを通じて四半期ごとに更新Windowsされます。 緊急の問題を解決するために、帯域外の更新を間に行う可能性があります。 Microsoft Teamsルーム アプリは常に製品ライフサイクルを使用し、アプリの最新バージョンと最後のバージョンだけがいつでもサポートされます。 Microsoft Teams Room アプリは、ルームで使用するために変更されたTeamsデスクトップ アプリの特定のバージョンをバンドルします。 新しいTeamsアプリは 2 週間ごとに更新されます。 更新プロセスの詳細[Teams確認してください](../teams-client-update.md)。 つまり、Teams Rooms アプリの最新バージョンは最大 6 つの Teams デスクトップ アプリ更新プログラムを使用できます。そのため、Teams Room アプリケーションを常に最新バージョンの Teams Rooms アプリに更新し続けることです。 

Teams Rooms のサポート構造は動的であり、最新バージョンの可用性に依存します。 最新ではないバージョンのアプリケーションでコードの欠陥が発生した場合は、最新バージョンをインストールして修正プログラムを受け取る必要があります。

すべてのリリースが、[Microsoft Teams Rooms リリース ノート](rooms-release-note.md)に記載されています。

> [!IMPORTANT]
> 以前のバージョンの Teams Room アプリケーションにインストールされた新しいデバイスをインストールする場合は、Windows 更新[](manual-update.md)プログラムをダウンロードする前に、アカウントの設定後にアプリケーションを手動で更新Windowsがあります。 これにより、correbt OS のバージョンと更新プログラムがデバイスに確実にインストールされます。  

## <a name="windows-10-release-support"></a>Windows 10 リリースのサポート

Microsoft Teams Rooms には、半期のチャネル サービス オプションに基づく Windows 10 IoT Enterprise または Windows 10 Enterprise SKU が必要です。 その他の Windows 10 エディションはサポートされていません。

- Windows 10 Enterprise Long-Term Servicing Branch (LTSB)/長期サービス チャネル (LTSC) エディション
- Windows 10 Internet of Things (IoT) Enterprise LTSB/LTSC エディション
- Windows 10 Pro エディションや Windows 10 Home エディションなどの、その他の Windows エディション

新Windows 10機能の更新プログラムは、Microsoft Teams Rooms デバイスではすぐに提供されません。 リリース情報ページに公開されている一般公開日から最大 6 か月以上の aAn[意図的な](/windows/release-information/)遅延Windows 10があります。 この時間は、Windows 10 Rooms アプリ、Microsoft Teams ハードウェア、認定オーディオ ビデオ周辺機器のリリース互換性を検証するために使用されます。 Windows 10 のメジャー リリースの各開発期間に検証が開始され、継続されます。 すべてのデバイス メーカーが自分たちのデバイス用の最新イメージを構築したことを検証し、Microsoft Teams でそれらのイメージを認定してテストするための余分な時間が必要です。 検証期間中、Microsoft Teams Room アプリでは、Windows [Update for Business](/windows/deployment/update/waas-manage-updates-wufb)グループ ポリシーを使用して、機能の更新Windows 10遅延します。 互換性の問題が発見され、解決されると、Microsoft Store での新しいアプリ リリースを通して、グループ ポリシーを更新することにより、ブロックが解除されます。 Microsoft Teams Rooms アプリを実行するデバイスは、夜間のメンテナンス再起動中に、適切な Windows 10 リリースに自動的に更新されます。 手動で更新プログラムを管理する必要があるお客様は、MSI バージョンを使用できます。  

> [!IMPORTANT]
> 検証期間中は、Microsoft Teams Rooms デバイスが、何らかの方法で、次の Windows 10 のリリースに更新 **されない** ようにする必要があります。 これには、グループ ポリシーの施行の無効化または System Center やその他のサードパーティ製デバイス管理サービスの使用が含まれます。 これらが原因で、Microsoft Teams Room アプリに問題が発生したり、デバイスが使用できなくなる可能性があります。  

次の表は、Microsoft Teams Roomsのサポートが確認されている Windows 10 の推奨バージョンとサポート対象バージョンを示しています。 すべての日付は、ISO 8601 形式 (YYYY-MM-DD) で表示されます。

|バージョン  |提供日   |Microsoft Teams Rooms のサポート状況   |Microsoft Teams Rooms の最小アプリケーション バージョン | 推奨 OS ビルド  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |サポート済み、 <br/>推奨|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |スキップ、 <br/> 非推奨 &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |サポート |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |非サポート  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |サポートされていません。 <br/>互換性に関する既知の&#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |非サポート                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |非サポート                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |非サポート                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 Rooms アプリケーションとの互換性の問題が見つかったので、バージョン 2004 Microsoft Teamsは推奨されません。 この特定の問題により、Microsoft Teams Rooms アプリケーションは夜間に再起動すると失敗します。 

&#x2781; Windows 10 Rooms アプリケーションとの互換性の問題が見つかったので、バージョン 1809 Microsoft Teamsは推奨されません。 この特定の問題により、Microsoft Teams Rooms アプリケーションは夜間に再起動すると失敗します。 この問題は、Windows 10 バージョン 1903 で解決されています。  

Windows 10 のサポートされているバージョンを使用している場合は、Microsoft Teams Rooms アプリの最新のアプリケーション更新プログラムを入手できます。  


## <a name="related-topics"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms リリース ノート](rooms-release-note.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
