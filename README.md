# UTOPIA Operating System Kernel

A simple operating system kernel project written in Rust, focused on learning and experimenting with operating system development.

## 🚀 Project Features

### Core Functionality
- **Modern Boot Support**: Supports both UEFI and BIOS boot
- **Framebuffer Graphics**: Custom font rendering and text display
- **Serial Debugging**: Complete serial communication and log output
- **Structured Logging**: Hierarchical logging system based on `log` crate
- **Testing Framework**: Integrated unit tests and integration tests

### Code Quality Improvements
- **Modular Design**: Clear module separation and responsibility division
- **Error Handling**: Comprehensive error type definitions and handling mechanisms
- **Constants Management**: Centralized constant definitions, avoiding magic numbers
- **Safe Programming**: Boundary checking and memory safety guarantees
- **Complete Documentation**: Detailed code comments and documentation

## 📁 Project Structure

```
utopia/
├── kernel/                 # Kernel code
│   └── src/
│       ├── main.rs        # Kernel entry point
│       ├── vga_buffer.rs  # VGA display driver
│       ├── serial.rs      # Serial communication
│       ├── logging.rs     # Logging system
│       ├── logo.rs        # Boot logo
│       ├── constants.rs   # Constants definition
│       ├── font.rs        # Font data
│       └── error.rs       # Error handling
├── os/                     # Bootloader
│   ├── src/main.rs        # Bootloader entry
│   └── build.rs           # Build script
└── font_converter/         # Font conversion tool
```

## 🛠️ Build and Run

### Prerequisites
- Rust toolchain (nightly)
- QEMU emulator
- bootloader dependencies

### Build Commands
```bash
# Build kernel
cargo build

# Run kernel (in QEMU)
cargo run --bin utopia

# Run tests
cargo test
```

### Development Environment Setup
```bash
# Install Rust nightly
rustup install nightly
rustup default nightly

# Add target platform
rustup target add x86_64-unknown-none

# Install QEMU
# Windows: Download and install QEMU
# Linux: sudo apt install qemu-system-x86
# macOS: brew install qemu
```

## 🔧 Latest Improvements

### Code Refactoring
1. **Modularization Improvements**
   - Created `constants.rs` module to manage all constants
   - Separated `font.rs` module for font data handling
   - Added `error.rs` module for unified error handling

2. **Enhanced Error Handling**
   - Defined `KernelError` enumeration type
   - Implemented `KernelResult<T>` type alias
   - Added `SafeWrite` trait for safe writing
   - Created error handling macros to simplify code

3. **Security Enhancements**
   - Added boundary checking to prevent buffer overflow
   - Implemented safe pixel operation functions
   - Provided safe print macros that won't panic

4. **Performance Optimization**
   - Reduced duplicate font data definitions
   - Optimized pixel rendering logic
   - Improved memory access patterns

### New Features
- `print_safe!` and `println_safe!` macros
- `serial_print_safe!` and `serial_println_safe!` macros
- Character printability checking
- Improved log initialization error handling

## 🎯 Future Plans

| Priority | Feature | Status | Description |
|----------|---------|--------|--------------|
| High | Screen Scrolling | ⏳ Planned | Implement proper screen scrolling functionality |
| High | Keyboard Input | ⏳ Planned | Add keyboard input support |
| Medium | Memory Management | ⏳ Planned | Implement basic memory management |
| Medium | Interrupt Handling | ⏳ Planned | Add interrupt processing |
| Low | File System | 🔮 Future | File system support |
| Low | Multitasking | 🔮 Future | Task scheduling |
| Low | Network Stack | 🔮 Future | Network protocol stack |
| Low | User Space | 🔮 Future | User space programs |

## 🤝 Contributing

1. Fork the project
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the GPL-2.0 License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Writing an OS in Rust](https://os.phil-opp.com/) - Excellent Rust operating system development tutorial
- [bootloader](https://github.com/rust-osdev/bootloader) - Rust bootloader
- Rust community support and contributions

---

**Note**: This is a learning project and is not suitable for production use.