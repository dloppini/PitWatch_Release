# PitWatch Release v1.0.23

**Release Date:** November 7, 2025  
**Version:** v1.0.23  
**Type:** Feature Release (UI/UX Improvements & Power Optimization)

---

## 🎯 Overview

This release focuses on **UI/UX improvements** and **power optimization** for the watch face. The tileview page transitions have been refined for a sharper, more responsive experience, and the watch face now includes early haptic feedback disabling to extend battery life.

---

## ✨ What's New

### UI/UX Improvements
- **🚀 Sharp Page Transitions**: Optimized tileview animation timing (100ms) for snappy, responsive page switching
- **⚡ No Momentum Scrolling**: Disabled scroll momentum for direct, precise page control
- **📱 Quick Snap**: Pages now snap quickly into position with minimal delay
- **🎯 Better Touch Response**: More tactile and immediate feedback when swiping between pages

### Power Optimization
- **🔋 Early Haptic Disable**: Haptic motor now disabled after 5 seconds of inactivity (previously 10 seconds)
- **💾 Battery Life Extension**: Estimated ~2% battery savings from haptic optimization
- **🔌 Smart Re-enable**: Haptics automatically re-enable on any touch interaction
- **⚡ Responsive Wake**: Haptics properly restored when waking from screen-off mode

---

## 📋 What's Changed

### Files Modified
- `examples/PitWatch/main.cpp` - Optimized tileview transition configuration
- `examples/PitWatch/A01b_FaceWatch.cpp` - Added early haptic disabling in watch face
- `examples/PitWatch/version.h` - Updated version to v1.0.23
- `tasks/BATTERY_OPTIMIZATION_TASKS.md` - Updated battery optimization task list

### Technical Details

#### Page Transition Configuration
```cpp
// Sharp, responsive transitions (100ms)
lv_obj_set_style_anim_time(tileview, 100, LV_PART_MAIN);

// Disabled momentum for direct control
lv_obj_clear_flag(tileview, LV_OBJ_FLAG_SCROLL_MOMENTUM);

// Quick snap to center
lv_obj_set_scroll_snap_x(tileview, LV_SCROLL_SNAP_CENTER);
```

#### Haptic Power Optimization
```cpp
// In inactivity_timer_cb() - disable after 5s
if (elapsed_ms > 5000 && !screen_off && !haptics_disabled) {
    watch.powerIoctl(WATCH_POWER_DRV2605, false);
    haptics_disabled = true;
}

// In touch event handler - re-enable immediately
if (!screen_off) {
    watch.powerIoctl(WATCH_POWER_DRV2605, true);
}
```

---

## 🎨 User Experience

### Before (v1.0.22)
- Page transitions: 200ms with momentum (smooth but slower)
- Haptics: Disabled only when screen turns off (10 seconds)
- Battery life: 8-12 hours (watch mode)

### After (v1.0.23)
- Page transitions: 100ms without momentum (sharp and responsive)
- Haptics: Disabled after 5 seconds of inactivity
- Battery life: ~2% improvement (estimated 8.2-12.2 hours)

---

## 📦 Installation

### OTA Update (Recommended)
1. Open PitWatch
2. Navigate to **OTA Settings** (gear icon → Settings)
3. Tap **CHECK UPDATES**
4. If v1.0.23 is available, tap **INSTALL UPDATE**
5. Wait for download and installation to complete
6. Device will restart automatically with new version

### Manual Update via PlatformIO
```bash
cd PitWatch
pio run --target upload --upload-port COM5
```

### Manual Flash via ESP Tool
1. Download `firmware.bin` from this release
2. Use ESP Flash Download Tool or esptool.py
3. Flash to your T-Watch S3 device at address 0x0

---

## 🐛 Bug Fixes
- None in this release

## 🚀 New Features
- Sharp page transitions (100ms)
- Early haptic power saving (5s vs 10s)

## ⚠️ Breaking Changes
- None

## 🔧 Known Issues
- None introduced in this release

---

## 📊 Build Information

- **Firmware Version:** v1.0.23
- **Build Environment:** PlatformIO
- **Target Board:** LilyGo T-Watch S3
- **LVGL Version:** 8.x
- **Compiler:** ESP-IDF with Arduino Framework
- **Build Date:** November 7, 2025

---

## 🔄 Upgrade Path

### From v1.0.22
- ✅ Direct upgrade supported
- ✅ All settings preserved
- ✅ No data loss
- ✅ OTA update available

### From Earlier Versions
- Upgrade to v1.0.22 first, then to v1.0.23 (or direct upgrade should work)

---

## 📝 Battery Optimization Status

This release implements **Task 1.2** from the Battery Optimization roadmap:

- ✅ **Phase 1 - Task 1.2 Complete**: Early haptic disable (5s idle)
- ⏳ **Phase 1 - Task 1.1 Pending**: Minute-based time updates
- ⏳ **Phase 1 - Task 1.3 Pending**: Battery indicator throttling (30s)

**Expected cumulative savings after Phase 1 complete:** +15-20% battery life

---

## 🎯 Testing Checklist

- [x] Page transitions work smoothly
- [x] No momentum scrolling
- [x] Quick snap to center position
- [x] Haptics disabled after 5 seconds
- [x] Haptics re-enabled on touch
- [x] Watch face functions normally
- [x] Battery indicator updates correctly
- [x] Time display accurate
- [x] Screen wake/sleep works properly
- [x] All pages accessible

---

## 👥 Contributors

- @dloppini - UI/UX improvements and power optimization

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 🔗 Resources

- **Documentation**: See project README.md
- **User Manual**: Available in 6 languages (EN, ES, FR, IT, DE, ZH)
- **Battery Optimization Guide**: `tasks/BATTERY_OPTIMIZATION_TASKS.md`
- **Issue Tracker**: GitHub Issues

---

## 💬 Feedback

Found a bug or have a feature request? Please open an issue on GitHub!

**Enjoy the improved responsiveness and extended battery life!** ⚡🔋
