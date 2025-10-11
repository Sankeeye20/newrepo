import signal
import time

def custom_sigint_handler(signum, frame):
    """
    Custom signal handler for SIGINT.
    """
    print("\nCaught SIGINT! Performing cleanup...")
    # Add your cleanup code here, e.g., closing files, releasing resources
    print("Exiting gracefully.")
    exit(0) # Exit the program after handling

# Register the custom handler for SIGINT
signal.signal(signal.SIGINT, custom_sigint_handler)

print("Press Ctrl+C to trigger the custom SIGINT handler.")
while True:
    print("Running...")
    time.sleep(1)
print('success')
