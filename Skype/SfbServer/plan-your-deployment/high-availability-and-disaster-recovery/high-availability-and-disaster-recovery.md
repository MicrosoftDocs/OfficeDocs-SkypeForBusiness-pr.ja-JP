---
title: ビジネスのサーバーに、Skype での高可用性と災害復旧を計画します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。
ms.openlocfilehash: 94db95c097fca62e31a01efd1d254ab6d3cd6d37
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996460"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>ビジネスのサーバーに、Skype での高可用性と災害復旧を計画します。
 
Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。 
  
高可用性は、1 つまたは複数のサーバーがダウンした場合でも、ビジネス サーバー サービスの Skype が利用可能であることを確認することを指します。 障害復旧とは、自然災害または人災が発生した場合であってもサービスの稼働を維持し、災害前からのデータを可能な限り多く維持することです。
  
Lync Server の以前のバージョンのように Skype ビジネス サーバー用のほとんどのサーバーの役割の主な高可用性機能はプールを使用してサーバーの冗長性 特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。 同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。
  
ビジネス サーバーの Skype は、リカバリ ・ オプションのフロント エンド プールの障害も提供します。 互いのバックアップとして機能するように、2 つのプールを別々の地理的地域にセットアップできます。 これによって、プールまたはサイト全体を停止させた場合に、バックアップ プールが両方のサイトのユーザーにサービスを継続して提供できます。
  
Skype ビジネス サーバーのでは、バック エンド サーバーの高可用性の 4 つのモードもがサポートされています: SQL のミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リングします。
  
> [!NOTE]
> SQL ミラーリング ビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リング手法は、ビジネス サーバー 2019 の Skype で優先します。

> [!NOTE]
> AlwaysOn 可用性グループは、永続的なチャット サーバーではサポートされていません。 
  
このセクションでは、これらの機能について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。 
  
## <a name="see-also"></a>関連項目

[フロントエンド プールの高可用性と管理](high-availability.md)
  
[ビジネス サーバーの前面の Skype で最後のプール災害復旧](disaster-recovery.md)
  
[Skype でプールの障害発生時にビジネス サーバー用のユーザー エクスペリエンス](user-experience.md)
  
[Skype の最後のサーバーの高可用性をビジネスのサーバーのバックアップします。](back-end-server.md)
  
[Skype で高可用性をビジネス サーバーの共有ファイル](file-sharing.md)