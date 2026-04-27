# 糖葫芦享屏 (THLPlay) - 产品技术文档

糖葫芦享屏 (THLPlay) 是一款专为 Apple 生态设计的高性能 AirPlay 镜像与音频接收解决方案。本产品采用私有优化协议栈，支持 4K 高清投屏与超低延迟音频流传输。

## 1. 产品核心特性

- **极致性能响应**:
  - **音频**: 基于 AudioQueue Services 的渲染引擎，内置 16 级高性能缓冲池，彻底消除杂音与延迟。
  - **视频**: 深度集成 `AVSampleBufferDisplayLayer` 硬件加速，支持 4K/60fps 镜像流。
- **底层网络优化**:
  - 针对 iOS/tvOS 沙箱环境优化的 `NWListenerBridge` 技术，绕过传统 Socket 限制，显著提升局域网设备搜索成功率与连接稳定性。
- **多端原生支持**:
  - 深度适配 iPhone, iPad, Apple TV 及 Mac (Catalyst)，提供一致的交互体验。
- **专业级 UI/UX**:
  - 全新毛玻璃（Glassmorphism）视觉体系，适配各平台最新系统风格。

## 2. 技术规格

- **应用层**: SwiftUI / Swift Concurrency
- **渲染引擎**: AVFoundation / AudioQueue 硬件加速
- **协议栈**:
  - 基于 C 语言深度定制的 RAOP、FairPlay、libplist 核心组件。
  - **THLPlayBridge**: 高性能 Objective-C 桥接层。
  - **NWListener**: 基于苹果原生 Network.framework 的现代传输层。

## 3. 开发与环境配置 (仅限内部人员)

### 环境要求
- Xcode 15.0 或更高版本
- iOS 14.0+ / tvOS 14.0+ / macOS 11.0+
- CocoaPods 1.12+

### 编译步骤
1. 打开终端，进入项目根目录。
2. 执行依赖安装：
   ```bash
   pod install
   ```
3. 使用 Xcode 打开生成的 `THLAirPlayApp.xcworkspace`。
4. 确保开发证书配置正确，选择目标设备进行编译运行。

## 4. 项目结构说明
- `THLAirPlayApp/`: SwiftUI 交互逻辑与业务代码。
- `Renderers/`: 音视频硬件加速渲染核心。
- `Sources/`: 桥接组件及 Network.framework 通讯层。
- `lib/`: 经过安全加固与性能优化的私有协议核心库。

---

## 5. 版权与许可

© 2026 糖葫芦享屏开发团队。保留所有权利。

[隐私政策 (Privacy Policy)](PRIVACY_POLICY.md)

本软件及其相关文档包含的所有技术细节、源代码及设计方案均为商业机密。未经书面授权，禁止以任何形式进行复制、分发、反编译或在第三方项目中使用。
