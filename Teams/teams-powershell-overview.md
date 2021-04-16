---
title: Microsoft Teams PowerShell の概要
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell コントロールを使用して Microsoft Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768356"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams PowerShell の概要

Microsoft Teams PowerShell は、PowerShell コマンド ラインから直接 Teams を管理するための一連のコマンドレットです。 .NET Standard で記述された Teams PowerShell は、Azure Cloud Shell を含むすべてのプラットフォームで、Windows、PowerShell 6.x 以上の PowerShell 5.1 で動作します。

PowerShell の使用を開始する前に、[それをインストール](teams-powershell-install.md)する必要があります。 

> [!WARNING]
> PowerShell 7 および Teams PowerShell には、既知の問題があります。 問題が解決されるまで PowerShell 5.1 の使用をお勧めします。

## <a name="releases"></a>リリース


Teams PowerShell は、2 つのリリース タイプで [PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams)を利用できます。

- **一般提供 (GA)**: 本番対応のコマンドレットであり、毎月更新されます。

- **パブリック プレビュー**: 機能にいち早くアクセスします。 GA よりも頻繁に更新される場合があります。

両方のリリースでの機能の追加と改善の詳細については、「[Teams PowerShell リリース ノート](teams-powershell-release-notes.md)」をご覧ください。


## <a name="manage-teams-with-powershell"></a>PowerShell で Teams を管理する

Teams PowerShell モジュールを使用して、Teams を完全に管理します。

- [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/): Teams PowerShell モジュールには、チーム、チャット、およびチャネルを管理するためのコマンドレットが含まれています。

> [!NOTE]
> [Teams PowerShell のパブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)バージョン 2.0 以上には、すべての Skype for Business Online Connector コマンドレットが含まれるので、Teams PowerShell 管理用の 1 つのモジュールが提供されます。

- [Skype for Business PowerShell コネクタ](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): Skype for Business PowerShell コネクタは、Teams PowerShell モジュールの一部になりました。

これらのモジュールを使用して Teams を管理するための完全なガイドについては、「[Teams PowerShell で Teams を管理する](teams-powershell-managing-teams.md)」をご覧ください。


## <a name="related-topics"></a>関連トピック

[Teams Powershell のインストール](teams-powershell-install.md)

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)

[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)
